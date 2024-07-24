cmake_minimum_required(VERSION 3.10)

project(QuotientFilter C)

set(SOURCES_FILES
        src/qf_improved.c
        src/murmur3.c)
set(HEADER_FILES src/qf_improved.h)

add_library(qf_static STATIC ${SOURCES_FILES})


target_include_directories(qf_static PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src)


target_link_libraries(qf_static m)

add_library(qf_shared SHARED ${SOURCES_FILES})


target_include_directories(qf_shared PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src)


target_link_libraries(qf_shared m)