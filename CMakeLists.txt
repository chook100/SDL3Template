cmake_minimum_required(VERSION 3.24)
project(SDL3Template LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 20)

include(FetchContent)

set(SDL_SHARED OFF CACHE BOOL "" FORCE)
set(SDL_STATIC ON  CACHE BOOL "" FORCE)
set(SDL_TEST_LIBRARY OFF CACHE BOOL "" FORCE)

FetchContent_Declare(
        SDL3
        GIT_REPOSITORY https://github.com/libsdl-org/SDL.git
        GIT_TAG        release-3.4.6
        GIT_SHALLOW    TRUE
        GIT_PROGRESS   TRUE
)
FetchContent_MakeAvailable(SDL3)

add_executable(SDL3Template src/main.cpp)
target_link_libraries(SDL3Template PRIVATE SDL3::SDL3)