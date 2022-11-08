##
## SPDX-License-Identifier: BSD-3-Clause
## Copyright (c) 2022 - present Mikael Sundell.
##

cmake_minimum_required(VERSION 3.23)
set( app_name "arri-logc" )

# project
project( "${app_name} project" )

# modules
set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/modules" )

# imath
find_package( Imath REQUIRED )
find_package( OIIO REQUIRED )
find_package( OCIO REQUIRED )

# package
add_executable( ${app_name} "arri-logc.cpp" )

include_directories (
    ${IMATH_INCLUDE_DIRS}
    ${OIIO_INCLUDE_DIRS}
    ${OCIO_INCLUDE_DIR}
)

target_link_libraries( ${app_name}
    ${IMATH_LIBRARIES}  
    ${OIIO_LIBRARIES}
    ${OCIO_LIBRARIES}
)
