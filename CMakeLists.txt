##############################################################################
# CMake
##############################################################################

cmake_minimum_required(VERSION 2.8.3)
project(feed_the_troll_msgs)

##############################################################################
# Dependencies
##############################################################################

find_package(catkin REQUIRED COMPONENTS
    message_generation
    uuid_msgs
)

##############################################################################
# Messgaes
##############################################################################

#add_action_files(
#  DIRECTORY action
#  FILES
#  AutonomousDocking.action
#)

#add_message_files(
#  DIRECTORY msg
#  FILES
#  BroadCastBehaviour.msg
#)

add_service_files(
  DIRECTORY srv
  FILES
    LoadFromRosParam.srv
    LoadFromYamlString.srv
    Unload.srv
)

#add_service_pair_files(
#  DIRECTORY pairs
#  FILES
#  DeliveryTask.pair
#)

generate_messages(
    DEPENDENCIES
        uuid_msgs
)

##############################################################################
# Package
##############################################################################

catkin_package(
    CATKIN_DEPENDS
        message_runtime
        uuid_msgs
)
