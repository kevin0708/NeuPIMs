CMAKE_MINIMUM_REQUIRED(VERSION 3.15)

# project setting
set(LIB_NAME "Simulator")

# set source and headers
file(GLOB_RECURSE SRC_FILES
  "${PROJECT_SOURCE_DIR}/src/*.h"
  "${PROJECT_SOURCE_DIR}/src/*.cc"
)

# we need remove main.cc from the list
list(FILTER SRC_FILES EXCLUDE REGEX ".*main.cc$")

# build
add_executable(${LIB_NAME} ${SRC_FILES} "${PROJECT_SOURCE_DIR}/src/main.cc")
add_library(${LIB_NAME}_lib ${SRC_FILES})
