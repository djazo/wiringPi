cmake_minimum_required(VERSION 3.10)
project(wiringPi)

execute_process(COMMAND cat ${CMAKE_SOURCE_DIR}/VERSION
  OUTPUT_VARIABLE WIRINGPI_VERSION
  OUTPUT_STRIP_TRAILING_WHITESPACE
  )

find_library(LIBM m REQUIRED)
find_library(LIBPTHREAD pthread REQUIRED)
find_library(LIBRT rt REQUIRED)
find_library(LIBCRYPT crypt REQUIRED)

add_directory(wiringPi)
add_directory(wiringPiD)
add_directory(devLib)
add_directory(gpio)

