cmake_minimum_required(VERSION 3.23)
project(cmake_test1)

set(CMAKE_CXX_STANDARD 20)

# set(CMAKE_INSTALL_PREFIX "${CMAKE_CURRENT_SOURCE_DIR}/installed")

include_directories(include)

add_library(clxxx_s STATIC src/TestPkg.cpp)

install(TARGETS clxxx_s EXPORT clxxx_s-targets  DESTINATION lib)

install(FILES include/TestPkg.h DESTINATION include)

install(EXPORT clxxx_s-targets FILE clxxx_s-config.cmake NAMESPACE mylib:: DESTINATION lib)
#install(FILES include/TestPkg.h DESTINATION include)