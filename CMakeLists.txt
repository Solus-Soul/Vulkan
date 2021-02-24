cmake_minimum_required(VERSION 3.13 FATAL_ERROR)

set(PROJECT_NAME Vulkan)
project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 17)

add_executable(${PROJECT_NAME}
    src/main.cpp
    )

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)


add_subdirectory(external/glfw)
target_link_libraries(${PROJECT_NAME} glfw)

add_subdirectory(external/glm)
target_link_libraries(${PROJECT_NAME} glm)

find_package(Vulkan)
if(Vulkan_FOUND)
    target_include_directories(${PROJECT_NAME} PRIVATE Vulkan::Vulkan)
    target_link_libraries(${PROJECT_NAME} Vulkan::Vulkan)
endif()
