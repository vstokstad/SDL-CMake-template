cmake_minimum_required(VERSION 3.19)
project(main)

#### buildoptions for Clion
#   -DSDL2_PATH="C:/lib/SDL2" -G "Visual Studio 16 2019" -A "x64"
####

set(CMAKE_CXX_STANDARD 20)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/include/sdl2)
#set(SDL2_PATH "C:/lib/SDL2")

#main exe
add_executable(main main.cpp include/sdl2.h)
#include include
target_include_directories(${PROJECT_NAME} PRIVATE ../include)

# Find SDL2, SDL2_image and SDL2_gfx libraries
set(SDL2_PATH "C:/lib/SDL2" CACHE BOOL "" FORCE)
find_package(SDL2 REQUIRED)

# Link SDL2::Main
#TODO: ADD : SDL2::Image and SDL2::GFX to our project
target_link_libraries(main SDL2::Main)