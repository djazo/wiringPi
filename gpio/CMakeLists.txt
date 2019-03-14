set(SRC
  gpio.c
  readall.c
  )

add_executable(gpio ${SRC})
target_include_directories(gpio PUBLIC
  .
  ../wiringPi
  ../wiringPiDev
  ../devLib
  )
target_link_libraries(gpio wiringPi wiringPiDev ${LIBPTHREAD} ${LIBRT} ${LIBM} ${LIBCRYPT})
set_property(TARGET gpio PROPERTY POSITION_INDEPENDENT_CODE ON)
install(TARGETS gpio
  DESTINATION bin
  )
