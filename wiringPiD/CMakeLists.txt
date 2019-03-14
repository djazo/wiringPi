set(SRC
  wiringpid.c
  network.c
  runRemote.c
  daemonise.c
  )

add_executable(wiringpid ${SRC})
set_property(TARGET wiringpid PROPERTY POSITION_INDEPENDENT_CODE ON)
target_include_directories(wiringpid PUBLIC
  ../wiringPi
  ../wiringPiDev
  .
  )
target_link_libraries(wiringpid wiringPi wiringPiDev ${LIBM} ${LIBPTHREAD} ${LIBRT} ${LIBCRYPT})
install(TARGETS wiringpid
  DESTINATION sbin/
  )
