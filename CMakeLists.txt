cmake_minimum_required(VERSION 2.8.3)
project(krl_msgs)


find_package(catkin REQUIRED genmsg actionlib_msgs actionlib geometry_msgs)

add_action_files(DIRECTORY action FILES LIN.action PTP.action)
add_service_files(DIRECTORY srvs FILES SetMaxVelPercent.srv SetTool.srv SetBase.srv SetToolBase.srv)
generate_messages(DEPENDENCIES actionlib_msgs geometry_msgs)

catkin_package(CATKIN_DEPENDS message_runtime)

install(FILES
  action/LIN.action action/PTP.action srvs/SetMaxVelPercent.srv srvs/SetTool.srv srvs/SetBase.srv srvs/SetToolBase.srv
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
