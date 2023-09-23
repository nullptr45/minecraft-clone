cmake_minimum_required(VERSION 3.16)
project(minecrap)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(SDL2 REQUIRED)

add_executable(minecrap)

file(GLOB_RECURSE MC_SRCS CONFIGURE_DEPENDS src/*.c)
target_sources(minecrap PRIVATE ${MC_SRCS})

target_include_directories(minecrap PRIVATE ${SDL2_INCLUDE_DIRS})
target_link_libraries(minecrap PRIVATE ${SDL2_LIBRARIES})
