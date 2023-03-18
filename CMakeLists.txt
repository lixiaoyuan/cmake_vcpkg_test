cmake_minimum_required(VERSION 3.23)
project(cmake_test1)

set(CMAKE_CXX_STANDARD 20)

include_directories(include)

add_library(clxxx SHARED src/TestPkg.cpp)