cmake_minimum_required(VERSION 3.23)
project(cmake_test1)

set(CMAKE_CXX_STANDARD 20)

# set(CMAKE_INSTALL_PREFIX "${CMAKE_CURRENT_SOURCE_DIR}/installed")

include_directories(include)

add_library(clib STATIC src/TestPkg.cpp)

install(TARGETS clib
        EXPORT clibTargets
        DESTINATION lib)

install(FILES include/TestPkg.h DESTINATION include)

#install(EXPORT clib-targets FILE clib-config.cmake NAMESPACE mylib:: DESTINATION lib)
install(EXPORT clibTargets FILE clibConfig.cmake NAMESPACE mylib:: DESTINATION lib)

#install (
#        FILES
#        "${CURRENT_PACKAGES_DIR}/lib/clibConfig.cmake"
#        DESTINATION "${CURRENT_PACKAGES_DIR}/share/${PORT}"
#)

#install(FILES include/TestPkg.h DESTINATION include)