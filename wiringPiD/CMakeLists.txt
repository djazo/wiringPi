set(SRC
  wiringpid.c
  network.c
  runRemote.c
  daemonise.c
  )

add_executable(wiringpid ${SRC})
target_include_directories(wiringpid ../wiringPi ../wiringPiDev .)
target_link_libraries(wiringpid wiringPi wiringPiDev ${LIBM} ${LIBPTHREAD} ${LIBRT} ${LIBCRYPT})
install(TARGETS wiringpid
  DESTINATION sbin/
  )
