cmake_minimum_required(VERSION 3.10)

project(your_project C)

add_executable(your_program main.c)

# Platform-independent custom target
add_custom_target(run
    COMMAND ${CMAKE_COMMAND} --build . --target your_program
    COMMAND ${CMAKE_BINARY_DIR}/your_program
    WORKING_DIRECTORY ${CMAKE_BINARY_DIR}
    DEPENDS your_program
)
