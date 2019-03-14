set(SRC
  gpio.c
  readall.c
  )

add_executable(gpio ${SRC})
target_include_directories(gpio . ../wiringPi ../wiringPiDev)
target_link_libraries(gpio wiringPi wiringPiDev ${LIBPTHREAD} ${LIBRT} ${LIBM} ${LIBCRYPT})
install(TARGETS gpio
  DESTINATION bin
  )
