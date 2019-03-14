
set(SRC
  ds1302.c
  gertboard.c
  lcd128x64.clcd.c
  maxdetect.c
  piFace.c
  piGlow.c
  piNes.c
  scrollPhat.c
)

set(HEADERS
  ds1302.h
  gertboard.h
  lcd.h
  lcd128x64.h
  maxdetect.h
  piFace.h
  piGlow.h
  piNes.h
  scrollPhat.h
)

add_library(wiringPiDev_obj OBJECT ${SRC})
target_include_directories(wiringPiDev_obj PUBLIC .)

add_library(wiringPiDev $<TARGET_OBJECTS:wiringPiDev_obj>)
target_link_libraries(wiringPiDev ${LIBPTHREAD})
set_target_properties(wiringPiDev PROPERTIES VERSION ${WIRINGPI_VERSION})
install(TARGETS wiringPiDev
  DESTINATION lib/
  )
