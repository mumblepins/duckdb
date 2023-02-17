cmake_minimum_required(VERSION 2.8.12)

project(AffineGapExtension)

include_directories(include)

add_library(affine_gap_extension STATIC affine-gap-extension.cpp)
set(PARAMETERS "-warnings")

build_loadable_extension(affine_gap ${PARAMETERS} affine-gap-extension.cpp)

install(
  TARGETS affine_gap_extension
  EXPORT "${DUCKDB_EXPORT_SET}"
  LIBRARY DESTINATION "${INSTALL_LIB_DIR}"
  ARCHIVE DESTINATION "${INSTALL_LIB_DIR}")
