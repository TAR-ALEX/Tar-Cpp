cmake_minimum_required(VERSION 3.16)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
project(example)
include_directories(
    "./vendor/include/"
    "./include/"
    # "./vendor/usr/include/x86_64-linux-gnu/"
    # "./vendor/usr/include/x86_64-linux-gnu/qt5/"
    # "./vendor/usr/include/x86_64-linux-gnu/qt5/*"
    "./src"
) 

file(GLOB_RECURSE APP_SOURCES CONFIGURE_DEPENDS "${PROJECT_SOURCE_DIR}/src/*")

add_executable(${PROJECT_NAME} ${APP_SOURCES})

target_link_libraries(${PROJECT_NAME} PRIVATE -lstdc++fs -lssl -lcrypto -llzma -lz -lbz2)


