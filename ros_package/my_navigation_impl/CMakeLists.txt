cmake_minimum_required(VERSION 2.8.3)

project(my_navigation_impl)

find_package(catkin REQUIRED)

catkin_package()

find_package(roslaunch)

catkin_install_python(PROGRAMS
  scripts/teleop_key.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

foreach(dir config launch meshes urdf)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)
