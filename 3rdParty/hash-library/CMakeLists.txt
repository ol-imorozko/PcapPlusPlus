cmake_minimum_required(VERSION 3.10)

project(hash-library LANGUAGES CXX)

# Create an object library
add_library(hash-library-obj OBJECT ./md5.cpp)

# Include directories for the object library, including EndianPortable's includes
target_include_directories(hash-library-obj PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}
  $<TARGET_PROPERTY:EndianPortable,INTERFACE_INCLUDE_DIRECTORIES>
)

# No 'target_link_libraries' call for object libraries as they can't link directly
