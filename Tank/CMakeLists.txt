if(NOT ENABLE_GUI)
  return()
endif()

option(BUILD_ROS_TANK "Building the ROS Tank files" OFF)
if(NOT BUILD_ROS_TANK)
  return()
endif()

if(UNIX)
  add_custom_target(
    symlink_to_ROS_TANK ALL
    COMMAND ${CMAKE_COMMAND} -E create_symlink
    ${CMAKE_CURRENT_SOURCE_DIR} ${CNOID_BINARY_SHARE_DIR}/Tank)
endif()

install(DIRECTORY
  project
  DESTINATION ${CNOID_SHARE_SUBDIR}/Tank)
