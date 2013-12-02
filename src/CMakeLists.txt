cmake_minimum_required(VERSION 2.8)
# Project Name
PROJECT(testogl)

#########################################################
# Include Files
#########################################################
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

add_executable(testogl main.cpp)

########################################################
# Linking & stuff
#########################################################

# create the program “testogl”
target_link_libraries(testogl ${OPENGL_LIBRARIES} ${GLEW_LIBRARY} ${GLFW_LIBRARIES})

if(CMAKE_GENERATOR STREQUAL Xcode)
  set_target_properties( testogl PROPERTIES
  RUNTIME_OUTPUT_DIRECTORY_DEBUG   ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}
  RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}
)
endif()
