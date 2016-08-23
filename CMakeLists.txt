cmake_minimum_required(VERSION 2.8.3)
project(krl_msgs)


find_package(catkin REQUIRED genmsg actionlib_msgs actionlib geometry_msgs)

add_action_files(DIRECTORY action FILES LIN.action PTP.action)
generate_messages(DEPENDENCIES actionlib_msgs geometry_msgs)

catkin_package()

install(FILES
  LIN.action PTP.action
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
