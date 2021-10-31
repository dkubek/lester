cmake_minimum_required(VERSION 3.11)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
endif()

# Setup the project
project(lester
    VERSION 0.1
    DESCRIPTION "Simple netwoek flow algorithm library."
    LANGUAGES CXX)

# Required setup for conan
include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

# Generate compile_commands.json
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# $source_files is a space-delimited list of filenames.
add_executable(lester src/main.cpp)
target_link_libraries(lester ${CONAN_LIBS})
