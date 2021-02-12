cmake_minimum_required(VERSION 3.19)
project(main)

set(CMAKE_CXX_STANDARD 20)
#set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${sdl_SOURCE_DIR}/cmake/sdl2")
list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake/sdl2)
set(SDL2_PATH "C:/lib/SDL2")


add_executable(main main.cpp include/sdl2.h)

target_include_directories(${PROJECT_NAME} PRIVATE ../include)
# Find SDL2, SDL2_image and SDL2_gfx libraries
set(SDL2_PATH "C:/lib/SDL2" CACHE BOOL "0" FORCE)
find_package(SDL2 REQUIRED)

# Link SDL2::Main, SDL2::Image and SDL2::GFX to our project


target_link_libraries(main SDL2::Main)