cmake_minimum_required(VERSION 3.11)

project(testProj)

include(FetchContent)

FetchContent_Declare(
  Catch2
  GIT_REPOSITORY "https://github.com/catchorg/Catch2"
  # Uncomment and set the following to a specific hash to
  # lock down to a specific commit and avoid contacting
  # the remote once we've already cloned/fetched it
  #GIT_TAG someGitHash
  )

FetchContent_GetProperties(Catch2) #mispelled name in original post
if(NOT catch2_POPULATED)   # name is lowercased
  FetchContent_Populate(Catch2)
  message(STATUS "Catch source dir: ${catch2_SOURCE_DIR}")
  message(STATUS "Catch binary dir: ${catch2_BINARY_DIR}")
  add_subdirectory(${catch2_SOURCE_DIR} ${catch2_BINARY_DIR}) # name is lowercased
endif()

add_executable(testExe
  main.cpp
  )

message(STATUS "Catch include dir: ${catch2_SOURCE_DIR}/include")

target_link_libraries(testExe Catch) #case sensitive!

