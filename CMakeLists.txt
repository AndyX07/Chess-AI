cmake_minimum_required(VERSION 3.15)
project(ChessEngine LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

file(GLOB SOURCES "src/*.cpp")

add_executable(ChessEngine ${SOURCES})

target_include_directories(ChessEngine PRIVATE ${CMAKE_SOURCE_DIR}/headers)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake")

if(WIN32)
    # !!! IMPORTANT !!!
    # Replace these with your own SDL2 installation paths
    # or set them when running cmake:
    # cmake -DSDL2_PATH="C:/Path/To/SDL2" -DSDL2_IMAGE_PATH="C:/Path/To/SDL2_image"
    set(SDL2_PATH "<YOUR_SDL2_PATH>" CACHE PATH "Path to SDL2 SDK")
    set(SDL2_IMAGE_PATH "<YOUR_SDL2_IMAGE_PATH>" CACHE PATH "Path to SDL2_image SDK")
endif()

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)

target_include_directories(ChessEngine PRIVATE ${SDL2_INCLUDE_DIR} ${SDL2_IMAGE_INCLUDE_DIR})
target_link_libraries(ChessEngine PRIVATE ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARIES})

file(COPY ${CMAKE_SOURCE_DIR}/images DESTINATION ${CMAKE_BINARY_DIR})