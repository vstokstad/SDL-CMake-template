cmake_minimum_required(VERSION 3.19)
project(sdl)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${sdl_SOURCE_DIR}/cmake")

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)

include_directories(${SDL2_INCLUDE_DIR})

target_link_libraries(target ${SDL2_LIBRARY})
add_executable(sdl main.cpp)