cmake_minimum_required(VERSION 3.22)
project(myapp)
set(CMAKE_CXX_STANDARD 11)

set(CMAKE_BUILD_TYPE Debug)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_executable(hello glad/glad.c src/textures2.cpp)

target_include_directories(hello PRIVATE include)

find_package(glfw3 3.3 REQUIRED)

target_link_libraries(hello glfw)

find_package(OpenGL REQUIRED)

target_link_libraries(hello OpenGL::GL)