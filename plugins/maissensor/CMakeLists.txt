# Copyright (C) 2016 Istituto Italiano di Tecnologia iCub Facility 
# Authors: Marco Randazzo
# CopyPolicy: Released under the terms of the LGPLv2.1 or later, see LGPL.TXT



PROJECT(Plugin_MaisSensor)

include(AddGazeboYarpPluginTarget)

set(controlBoard_source     src/MaisSensor.cc
                            src/MaisSensorDriver.cpp
                            src/MaisSensorDeviceDriver.cpp)

set(controlBoard_headers    include/gazebo/MaisSensor.hh
                            include/yarp/dev/MaisSensorDriver.h)
                            
                            

add_gazebo_yarp_plugin_target(LIBRARY_NAME maissensor
                              INCLUDE_DIRS include/gazebo include/yarp/dev
                              SYSTEM_INCLUDE_DIRS ${GAZEBO_YARP_COMMON_HEADERS} ${Boost_INCLUDE_DIRS} ${GAZEBO_INCLUDE_DIRS}  ${SDFORMAT_INCLUDE_DIRS} ${PROTOBUF_INCLUDE_DIRS}
                              LINKED_LIBRARIES gazebo_yarp_lib_common gazebo_yarp_singleton ${YARP_LIBRARIES} ${GAZEBO_LIBRARIES} ${Boost_LIBRARIES}
                              HEADERS ${controlBoard_headers}
                              SOURCES ${controlBoard_source}
                            )
