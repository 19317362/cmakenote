
cmake_minimum_required(VERSION 3.10)

message("Using CMake version ${CMAKE_VERSION}")

if(NOT POLICY CMP0048)
  cmake_policy(SET CMP0048 NEW)
endif()


message("Before 'project':")
message("  C: '${CMAKE_C_COMPILER}'")
message("  C++: '${CMAKE_CXX_COMPILER}'")

message("  Source: ${PROJECT_SOURCE_DIR}")
message("  Binary: ${PROJECT_BINARY_DIR}")
message("  Version: ${PROJECT_VERSION}")
message("  Version (alt): ${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH}")

project(foo VERSION 1.2.7)
# Such form will be used widely in examples in cases when we don’t need to build targets.
# project(foo LANGUAGES NONE)

message("After 'project':")
message("  C: '${CMAKE_C_COMPILER}'")
message("  C++: '${CMAKE_CXX_COMPILER}'")
message("  Source: ${PROJECT_SOURCE_DIR}")
message("  Binary: ${PROJECT_BINARY_DIR}")
message("  Version: ${PROJECT_VERSION}")
message("  Version (alt): ${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH}")


message("From top level:")
message("  Source (general): ${PROJECT_SOURCE_DIR}")
message("  Source (foo): ${foo_SOURCE_DIR}")

if(NOT CMAKE_VERSION VERSION_LESS "3.0") # means 'NOT version < 3.0', i.e. 'version >= 3.0'
  # Code with 3.0 features
endif()



add_library(main main.cpp)

add_subdirectory(boo)
