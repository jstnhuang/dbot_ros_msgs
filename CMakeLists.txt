cmake_minimum_required(VERSION 2.8.3)
project(dbot_ros_msgs)

find_package(catkin REQUIRED
  actionlib
  geometry_msgs
  sensor_msgs
  std_msgs
  message_generation
)

################################################
## Declare ROS messages, services and actions ##
################################################

## Generate messages in the 'msg' folder
add_message_files(
  FILES
  ObjectOri.msg
  ObjectState.msg
  ObjectsState.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  RunObjectTracker.srv
  TrackObject.srv
  FindObject.srv
  MultiTrack.srv
)

add_action_files(
  FILES
  InitializeObject.action
)

generate_messages(
  DEPENDENCIES
    actionlib_msgs
    std_msgs
    geometry_msgs
    sensor_msgs
)


###################################
## catkin specific configuration ##
###################################
catkin_package(
  CATKIN_DEPENDS
    actionlib
)

