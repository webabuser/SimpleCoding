#cmake не различает регистр
cmake_minimum_required(VERSION 3.13 FATAL_ERROR)

set(PROJECT_NAME SimpleCoding) #Setting the various of project name
project(${PROJECT_NAME})	

add_executable(${PROJECT_NAME} src/main.cpp)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)

#Add the root directory of the GLFW source tree to your project. This will add #the glfw target to your project.

add_subdirectory(external/glfw)
target_link_libraries(${PROJECT_NAME} glfw)

add_subdirectory(external/glad)
target_link_libraries(${PROJECT_NAME} glad)