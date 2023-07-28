cmake_minimum_required(VERSION 3.22)
project(catch2_vendor CXX)

find_package(ament_cmake REQUIRED)
find_package(ament_cmake_vendor_package REQUIRED)

find_package(Catch2 3.4.0 QUIET)

ament_vendor(catch2_vendor
  SATISFIED ${catch2_FOUND}
  VCS_URL https://github.com/catchorg/Catch2.git
  VCS_VERSION v3.4.0
)

ament_package(CONFIG_EXTRAS_POST "catch2_vendor-extras.cmake")