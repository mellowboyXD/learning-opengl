cmake_minimum_required(VERSION 3.16)
project(LearnOpenGL_begin C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(DEPS_DIR ${CMAKE_SOURCE_DIR}/deps)

find_package(OpenGL REQUIRED)

add_executable(ch1_app
        src/main.cpp
        src/glad.c
)

target_include_directories(ch1_app PRIVATE
        ${DEPS_DIR}/include
)

target_link_directories(ch1_app PRIVATE
        ${DEPS_DIR}/lib
)

target_link_libraries(ch1_app PRIVATE
        glfw3
        OpenGL::GL
)
