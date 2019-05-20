cmake_minimum_required(VERSION 2.8)

set(PROJECT_NAME "Net")

project(${PROJECT_NAME})


include_directories(
    "${CMAKE_SOURCE_DIR}/libs/libuv/include"
    "${CMAKE_SOURCE_DIR}/libs/OpenSSL/include"
)

link_directories(
    "${CMAKE_SOURCE_DIR}/libs/libuv/x64"
    "${CMAKE_SOURCE_DIR}/libs/OpenSSL/lib"
)


FILE(GLOB_RECURSE DIR_SRC ./src/*.*)
source_group("src" FILES ${DIR_SRC})
add_library(${PROJECT_NAME} ${DIR_SRC})


target_link_libraries(${PROJECT_NAME} "libuv.lib")


