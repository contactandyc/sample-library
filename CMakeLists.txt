cmake_minimum_required(VERSION 3.16)
project(PROJECT_CAMEL VERSION VERSION LANGUAGES C)
set(CMAKE_C_STANDARD 11)

# Library
add_library(${PROJECT_NAME}
    src/sample.c
)

target_include_directories(${PROJECT_NAME} PUBLIC include)

# Example application
add_executable(example_app examples/minimal_example.c)

target_link_libraries(example_app PRIVATE ${PROJECT_NAME})

# Testing
include(CTest)
if(BUILD_TESTING)
    add_subdirectory(tests)
endif() 