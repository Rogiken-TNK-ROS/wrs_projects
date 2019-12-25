if(NOT ENABLE_GUI)
  return()
endif()

option(BUILD_TNK_MODEL "Building the TNKModel files" OFF)
if(NOT BUILD_TNK_MODEL)
  return()
endif()

if(UNIX)
  add_custom_target(
    symlink_to_TNK_MODEL ALL
    COMMAND ${CMAKE_COMMAND} -E create_symlink
    ${CMAKE_CURRENT_SOURCE_DIR} ${CNOID_BINARY_SHARE_DIR}/TNKModel)
endif()

install(DIRECTORY
  model
  project
  DESTINATION ${CNOID_SHARE_SUBDIR}/TNKModel)
