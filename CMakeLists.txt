cmake_minimum_required(VERSION 3.6)
project(QtGuiTestUtils CXX)
set(CMAKE_CXX_STANDARD 17)

find_package(Qt5 COMPONENTS Core Widgets Gui Test REQUIRED)

FILE (GLOB_RECURSE  GUITestUtilsSources
    GUITestUtils.h
)

add_library(GUITestUtils INTERFACE)
target_link_libraries(GUITestUtils INTERFACE Qt5::Gui Qt5::Widgets Qt5::Test)
target_include_directories(GUITestUtils INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>/
)
