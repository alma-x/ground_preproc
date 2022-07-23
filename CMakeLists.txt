cmake_minimum_required(VERSION 3.0.2)
project(ground_preproc)

# add_compile_options(-std=c++11)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
 # cv2
  #matplotlib
  #numpy
  #roscpp
  rospy
  sensor_msgs
  std_msgs
  message_generation
  #time
)

add_library(time STATIC IMPORTED)


catkin_package(
)




include_directories(
  ${catkin_INCLUDE_DIRS}
)


# TODO: find a better way to find libraries
catkin_install_python(
 PROGRAMS
  scripts/image_filter.py
  scripts/noise_simulation.py
  scripts/preprocessor.py
  scripts/lib_filters.py
  scripts/lib_histograms.py
 DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)


install(
 DIRECTORY
   launch
 DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
 )

