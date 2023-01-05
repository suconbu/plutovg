cmake_minimum_required(VERSION 3.3)

if(CMAKE_SOURCE_DIR STREQUAL CMAKE_CURRENT_SOURCE_DIR)
    set(PLUTOVG_STANDALONE TRUE)
endif()

option(PLUTOVG_BUILD_EXAMPLES "Build the examples" ${PLUTOVG_STANDALONE})

set(CMAKE_C_STANDARD 11)

project(plutovg C)

add_library(plutovg STATIC)

add_subdirectory(include)
add_subdirectory(source)
if(PLUTOVG_BUILD_EXAMPLES)
    add_subdirectory(example)
endif()
