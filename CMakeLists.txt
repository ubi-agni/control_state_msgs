cmake_minimum_required(VERSION 2.8.3)
project(control_state_msgs)

find_package(catkin REQUIRED COMPONENTS message_generation actionlib_msgs)

################################################
## Declare ROS messages, services and actions ##
################################################

# Generate messages in the 'msg' folder
add_message_files(
  FILES
  ControlState.msg
)

# Generate services in the 'srv' folder
add_service_files(
  FILES
  SwitchControlState.srv
)

# Generate services in the 'action' folder
add_action_files(DIRECTORY action FILES SwitchControlState.action)


## Generate added messages, services and actionlibs with any dependencies listed here
generate_messages(DEPENDENCIES actionlib_msgs)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if your package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES control_state_msgs
  CATKIN_DEPENDS message_runtime actionlib_msgs
#  DEPENDS system_lib
)
