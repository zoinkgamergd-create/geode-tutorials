cmake_minimum_required(VERSION 3.21)
cmake_policy(VERSION 3.21)

project(click_animations VERSION 1.0.0)

if (NOT DEFINED ENV{GEODE_SDK})
    message(FATAL_ERROR "Please define GEODE_SDK environment variable")
else()
    message(STATUS "Found Geode: $ENV{GEODE_SDK}")
endif()

add_subdirectory($ENV{GEODE_SDK} ${CMAKE_CURRENT_BINARY_DIR}/geode)

file(GLOB SOURCES src/*.cpp)
add_geode_mod(click_animations ${SOURCES})
