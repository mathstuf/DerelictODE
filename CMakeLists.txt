cmake_minimum_required(VERSION 2.8.12)
project(DerelictODE D)
list(APPEND CMAKE_MODULE_PATH
    "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

find_package(Derelict REQUIRED
    COMPONENTS
        util)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}/source")
add_library(DerelictODE STATIC
    source/derelict/ode/functions.d
    source/derelict/ode/ode.d
    source/derelict/ode/types.d)
target_link_libraries(DerelictODE
    Derelict::util)
