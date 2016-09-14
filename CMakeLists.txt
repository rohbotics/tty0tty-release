cmake_minimum_required(VERSION 2.8.3)
project(tty0tty)

find_package(catkin REQUIRED)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES tty0tty
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -O2 -D_GNU_SOURCE -Wno-unused-but-set-variable")
add_executable(tty0tty tty0tty.c)

target_link_libraries(tty0tty
  ${catkin_LIBRARIES}
)

#############
## Install ##
#############

## Mark executables and/or libraries for installation
install(TARGETS tty0tty tty0tty
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
