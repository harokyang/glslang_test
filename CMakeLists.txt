# CMakeList.txt : CMake project for CMakeProject1, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.12)

set(CMAKE_CXX_STANDARD 17)

project(test CXX)

# Add source to this project's executable.
add_executable (CMakeProject1 "CMakeProject1.cpp" "CMakeProject1.h")

set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

# TODO: Add tests and install targets if needed.
find_package(glslang REQUIRED)
message("glslang: ${glslang_FOUND}")
target_link_libraries(CMakeProject1 PRIVATE glslang::glslang glslang::SPIRV)
target_include_directories(CMakeProject1 PRIVATE "D:\\git\\vcpkg\\installed\\x64-windows\\include")