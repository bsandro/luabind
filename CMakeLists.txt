cmake_minimum_required(VERSION 2.6)

project(luabind CXX)

find_package(Boost 1.34.0 REQUIRED)
find_package(Lua51 REQUIRED)
add_subdirectory(src)
