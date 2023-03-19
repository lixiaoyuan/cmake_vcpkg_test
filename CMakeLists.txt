cmake_minimum_required(VERSION 3.23)
project(cmake_test1)

set(CMAKE_CXX_STANDARD 20)

include_directories(include)

add_library(clxxx_s STATIC src/TestPkg.cpp)

# set(CMAKE_INSTALL_PREFIX "${CMAKE_CURRENT_SOURCE_DIR}/installed")

install(TARGETS clxxx_s  DESTINATION lib)

install(FILES include/TestPkg.h DESTINATION include)

export(TARGETS clxxx_s FILE clxxx_s-config.cmake)
#install(FILES include/TestPkg.h DESTINATION include)