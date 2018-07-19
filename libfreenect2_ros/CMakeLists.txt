cmake_minimum_required(VERSION 2.8.3)
project(libfreenect2_ros CXX)

# See https://cmake.org/cmake/help/v3.0/module/ExternalProject.html
include(ExternalProject)


# Nice debug trick ...
#get_cmake_property(_variableNames VARIABLES)
#list (SORT _variableNames)
#foreach (_variableName ${_variableNames})
#    message(STATUS "${_variableName}=${${_variableName}}")
#endforeach()


# compile libfreenect2
externalproject_add(libfreenect2
  #PREFIX ${CMAKE_CURRENT_SOURCE_DIR}/..
  
  #--Download step--------------
  # Interesting ...
  #GIT_REPOSITORY https://github.com/OpenKinect/libfreenect2.git

  #--Configure step-------------
  SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/./libfreenect2
  CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX} -DENABLE_CXX11=ON -DENABLE_OPENCL=ON -DCUDA_PROPAGATE_HOST_FLAGS=off
  
  #--Build step-----------------
  BUILD_COMMAND make

  #--Install step---------------
  INSTALL_COMMAND make install DESTDIR=$ENV{DESTDIR}
  # &&  sudo cp ${CMAKE_CURRENT_SOURCE_DIR}/../libfreenect2/platform/linux/udev/90-kinect2.rules /etc/udev/rules.d/ 
)

# what follows is to make catkin happy about this pseudo-package
# cmake pkg-config libturbojpeg libglfw3-dev libopenni2-dev libusb-1.0-dev cuda_latest opencl_latest 
find_package(catkin REQUIRED COMPONENTS      )

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES kinect2_bridge
#  CATKIN_DEPENDS kinect2_registration
#  DEPENDS libfreenect2_ros
)

