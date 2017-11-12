cmake_minimum_required(VERSION 2.8)

# Options. Turn on with 'cmake -Dmyvarname=ON'.
option(test "Build all tests." OFF) # Makes boolean 'test' available.

# Make PROJECT_SOURCE_DIR, PROJECT_BINARY_DIR, and PROJECT_NAME available.
set(PROJECT_NAME MyProject)
project(${PROJECT_NAME})

set(CMAKE_CXX_FLAGS "-g -Wall")

#set(SOURCES src/project1.cpp src/main.cpp)
include_directories(include)


################################
# Normal Libraries & Executables
################################
add_library(project1_lib src/project1.cpp)
add_executable(project1 src/main.cpp)


target_link_libraries(project1 project1_lib)

