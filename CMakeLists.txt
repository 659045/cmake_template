cmake_minimum_required(VERSION 3.10)

project(your_program C)

add_executable(your_program main.c)

# Custom target that works with VS Code build types
add_custom_target(run
    COMMAND ${CMAKE_COMMAND} --build . --target ${PROJECT_NAME}
    COMMAND ${CMAKE_BINARY_DIR}/${CMAKE_BUILD_TYPE}/${PROJECT_NAME}
    WORKING_DIRECTORY ${CMAKE_BINARY_DIR}
    DEPENDS your_program
)
