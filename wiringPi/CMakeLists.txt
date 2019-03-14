# wiringPi library

set(SRC
  bmp180.c
  drcSerial.c
  max31855.c
  mcp23008.c
  mcp23s08.c
  mcp3002.c
  pcf8574.c
  piHiPri.c
  pseudoPins.c
  sn3218.c
  sr595.c
  wiringPiSPI.c
  wiringSerial.c
  wpiExtensions.c
  ads1115.c
  drcNet.c
  ds18b20.c
  htu21d.c
  max5322.c
  mcp23016.c
  mcp23017.c
  mcp23s17.c
  mcp3004.c
  mcp3422.c
  mcp4802.c
  pcf8591.c
  piThread.c
  rht03.c
  softPwm.c
  softTone.c
  wiringPi.c
  wiringPiI2C.c
  wiringShift.c
)

set(HEADERS
  ads1115.h
  bmp180.h
  drcNet.h
  drcSerial.h
  ds18b20.h
  htu21d.h
  max31855.h
  max5322.h
  mcp23008.h
  mcp23016.h
  mcp23016reg.h
  mcp23017.h
  mcp23s08.h
  mcp23s17.h
  mcp23x08.h
  mcp23x0817.h
  mcp3002.h
  mcp3004.h
  mcp3422.h
  mcp4802.h
  pcf8574.h
  pcf8591.h
  pseudoPins.h
  rht03.h
  sn3218.h
  softPwm.h
  softServo.h
  softTone.h
  sr595.h
  wiringPi.h
  wiringPiI2C.h
  wiringPiSPI.h
  wiringSerial.h
  wiringShift.h
  wpiExtensions.h
)

add_library(wiringPi_obj OBJECT ${SRC})
target_include_directories(wiringPi_obj PUBLIC .)
set_property(TARGET wiringPi_obj PROPERTY POSITION_INDEPENDENT_CODE ON)
add_library(wiringPi $<TARGET_OBJECTS:wiringPi_obj>)
target_link_libraries(wiringPi ${LIBM} ${LIBPTHREAD} ${LIBRT} ${LIBCRYPT})
set_target_properties(wiringPi PROPERTIES VERSION ${WIRINGPI_VERSION})
install(TARGETS wiringPi
  DESTINATION lib/
  )
