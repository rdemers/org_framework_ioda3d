# The Flutter tooling requires that developers have CMake 3.10 or later
# installed. You should not increase this version, as doing so will cause
# the plugin to fail to compile for some customers of the plugin.
cmake_minimum_required(VERSION 3.10)

project(ioda3d_library VERSION 0.0.1 LANGUAGES C)

add_library(ioda3d SHARED
  "ioda3d.c"
)

set_target_properties(ioda3d PROPERTIES
  PUBLIC_HEADER ioda3d.h
  OUTPUT_NAME "ioda3d"
)

target_compile_definitions(ioda3d PUBLIC DART_SHARED_LIB)
