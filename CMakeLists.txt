cmake_minimum_required(VERSION 2.8.6)

project(meshLib CXX)

# set the path for custom cmake scripts
set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/build-aux/cmake")

# include common scripts
include(GroupSourcesByFilesystem)
include(CheckIncludeFiles)

option(BUILD_MESHLIB_TOOLS
    "Explicitly force building of tools" OFF)

include_directories(
    ${PROJECT_SOURCE_DIR}
)

add_subdirectory(meshLib)

if(BUILD_MESHLIB_TOOLS)
    add_subdirectory(tools)
endif()
