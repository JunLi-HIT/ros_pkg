cmake_minimum_required(VERSION 2.8.3)
project(husky_highlevel_controller)

## Use C++11
add_definitions(--std=c++11)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  roscpp
  sensor_msgs
  nav_msgs
  geometry_msgs
  tf2_geometry_msgs
  tf
  std_srvs
)

###################################
## catkin specific configuration ##
###################################
catkin_package(
  INCLUDE_DIRS
    include
#  LIBRARIES
  CATKIN_DEPENDS 
    roscpp
    sensor_msgs
    nav_msgs
    geometry_msgs
    tf2_geometry_msgs
    std_srvs
#  DEPENDS 
)

###########
## Build ##
###########
include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

add_executable(${PROJECT_NAME}
  src/${PROJECT_NAME}_node.cpp
  src/HuskyHighlevelController.cpp
)

target_link_libraries(${PROJECT_NAME}
  ${catkin_LIBRARIES}
)

#add_executable(ekf_localization
#  src/ekf_localization_node.cpp
#  src/EkfLocalization.cpp
#)

#target_link_libraries(ekf_localization
#  ${catkin_LIBRARIES}
#)

