cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)
include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/SVolkoff/hunter/archive/v0.19.188.1.tar.gz"
    SHA1 "dbd311601308b9bf8c3793567e612dc8fd0e6e4d"
)

project(demo)

hunter_add_package(list)
find_package(list)
add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/sources/demo.cpp)
target_link_libraries(demo list)

install(TARGETS demo RUNTIME DESTINATION bin)
