# Copyright (C) 2007-2016 Istituto Italiano di Tecnologia ADVR & iCub Facility & RBCS Department
# Authors: Enrico Mingo, Alessio Rocchi, Mirko Ferrati, Silvio Traversaro, Alessandro Settimi, Francesco Romano and Nuno Guedelha
# CopyPolicy: Released under the terms of the LGPLv2.1 or later, see LGPL.TXT


PROJECT(Plugin_distributedinertials)

include(AddGazeboYarpPluginTarget)


add_gazebo_yarp_plugin_target(LIBRARY_NAME distributedinertials
                              INSTALL_DESTINATION ${CMAKE_INSTALL_LIBDIR}
                              INCLUDE_DIRS include/gazebo include/yarp/dev
                              SYSTEM_INCLUDE_DIRS ${GAZEBO_YARP_COMMON_HEADERS} ${Boost_INCLUDE_DIRS} ${GAZEBO_INCLUDE_DIRS}  ${SDFORMAT_INCLUDE_DIRS} ${PROTOBUF_INCLUDE_DIRS}
                              LINKED_LIBRARIES gazebo_yarp_lib_common gazebo_yarp_singleton ${YARP_LIBRARIES} ${GAZEBO_LIBRARIES} ${Boost_LIBRARIES}
                              HEADERS include/gazebo/inertialMTBPart.hh
                                      include/yarp/dev/inertialMTBPartDriver.h
                              SOURCES src/inertialMTBPart.cc
                                      src/inertialMTBPartDriver.cpp
                                 )

