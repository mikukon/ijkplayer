cmake_minimum_required(VERSION 3.4.1)

add_library(android-ndk-profiler
            STATIC
            ${CMAKE_CURRENT_SOURCE_DIR}/prof.c)