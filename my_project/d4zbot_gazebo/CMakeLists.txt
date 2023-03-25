cmake_minimum_required(VERSION 3.0.2)
project(d4zbot_gazebo)

find_package(catkin REQUIRED)

catkin_package()

install(
  DIRECTORY worlds
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(
  FILES launch/d4zbot_empty_world.launch
        launch/spawn_d4zbot.launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)

if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)
  roslaunch_add_file_check(launch/d4zbot_empty_world.launch)
  roslaunch_add_file_check(launch/spawn_d4zbot.launch)
endif()