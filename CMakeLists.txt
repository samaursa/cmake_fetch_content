cmake_minimum_required(VERSION 3.11)

project(testProj)

include(FetchContent)

FetchContent_Declare(
  Catch2
  GIT_REPOSITORY "https://github.com/catchorg/Catch2"
  )

FetchContent_GetProperties(Catch2) #mispelled name in original post
if(NOT Catch2_POPULATED)
  FetchContent_Populate(Catch2)
  message(STATUS "Catch source dir: ${catch2_SOURCE_DIR}")
  message(STATUS "Catch binary dir: ${catch2_BINARY_DIR}")
  add_subdirectory(${catch2_SOURCE_DIR} ${catch2_BINARY_DIR}) #can be case insensitive
endif()

add_executable(testExe
  main.cpp
  )

message(STATUS "Catch include dir: ${catch2_SOURCE_DIR}/include")

target_link_libraries(testExe Catch) #case sensitive!

