cmake_minimum_required(VERSION 2.8.3)
project(pedsim_msgs)

# message and service dependencies
set( MESSAGE_DEPENDENCIES
    std_msgs
    geometry_msgs
)

find_package(catkin REQUIRED 
  COMPONENTS
  message_generation
  ${MESSAGE_DEPENDENCIES}
)

include_directories(${catkin_INCLUDE_DIRS})
link_directories(${catkin_LIBRARY_DIRS})

## Generate messages in the 'msg' folder
add_message_files( DIRECTORY msg
  FILES
  AgentState.msg
  AllAgentsState.msg
)



# generate the messages
generate_messages(DEPENDENCIES ${MESSAGE_DEPENDENCIES})

#Declare package run-time dependencies
catkin_package( CATKIN_DEPENDS message_runtime ${MESSAGE_DEPENDENCIES})