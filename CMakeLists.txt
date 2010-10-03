# Copyright (C) 2007-2009 LuaDist.
# Created by David Manura
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

PROJECT(boostmathspecialfunctions CXX)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
INCLUDE(dist.cmake)

# Find Boost headers (only headers required -- does not need to be compiled)
#FIND_PACKAGE (Boost REQUIRED)
SET (Boost_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR})
INCLUDE_DIRECTORIES(${Boost_INCLUDE_DIR})

# Build
ADD_LUA_MODULE(special_functions src/special_functions)

# Install all files and documentation
INSTALL (TARGETS special_functions DESTINATION ${INSTALL_CMOD}/boost/math/)
INSTALL (DIRECTORY doc/ DESTINATION ${INSTALL_DOC} PATTERN ".svn" EXCLUDE)
INSTALL (DIRECTORY tests/ DESTINATION ${INSTALL_TEST} PATTERN ".svn" EXCLUDE)
INSTALL (FILES README COPYRIGHT DESTINATION ${INSTALL_DATA})
