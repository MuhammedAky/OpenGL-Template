cmake_minimum_required(VERSION 3.14)
project(test_template VERSION 1.0)

cmake_policy(SET CMP0072 NEW)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenGL REQUIRED)

add_subdirectory(dependencies/glfw)

add_executable(test
    src/config.h
    src/main.cpp 
    src/glad.c
)

target_include_directories(test PRIVATE
    dependencies
    src
)

target_link_libraries(test PRIVATE
    glfw
    OpenGL::GL
)
