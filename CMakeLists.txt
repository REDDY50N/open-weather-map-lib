cmake_minimum_required(VERSION 3.24)
project(owm-lib VERSION 2.0.0 LANGUAGES CXX)

message(STATUS "Building Project: ${PROJECT_NAME}")

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS -rdynamic)
set(CMAKE_CXX_FLAGS -g3)
set(CMAKE_CXX_FLAGS -Wall)      # enable most warning
set(CMAKE_CXX_FLAGS -Wextra)    # enable extra warnings

#add_compile_options(-Wall)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt6 COMPONENTS Widgets Network Core)
if (NOT Qt6_FOUND)
    find_package(Qt5 5.15 REQUIRED COMPONENTS Widgets Network Core)
endif()


# Option to build as lib OR executable
option(BUILD_AS_LIBRARY "Build as a library" ON)

set(EXEC_NAME ${PROJECT_NAME})

if (BUILD_AS_LIBRARY)
    add_library(${EXEC_NAME} SHARED)
    message(STATUS "Building ${EXEC_NAME} as a library")
else()
    add_executable(${EXEC_NAME} src/main.cpp)
    message(STATUS "Building ${EXEC_NAME} as an executable")
endif()

add_subdirectory(src)

target_link_libraries(${EXEC_NAME} PRIVATE
        Qt::Core
        Qt::Gui
        Qt::Widgets
        Qt::Network
)
