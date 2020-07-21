cmake_minimum_required(VERSION 3.12)

project(test)

add_library(alphabeta)
find_package(sharedstatic)
target_link_libraries(alphabeta PUBLIC sharedstatic::sharedstatic_shared)
target_link_libraries(alphabeta PUBLIC sharedstatic::sharedstatic_static)
target_include_directories(
  alphabeta
  PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/include>
  $<INSTALL_INTERFACE:include>
  )
target_sources(alphabeta PRIVATE ${CMAKE_CURRENT_LIST_DIR}/src/source1.cpp)
target_sources(alphabeta PRIVATE ${CMAKE_CURRENT_LIST_DIR}/src/source2.cpp)

