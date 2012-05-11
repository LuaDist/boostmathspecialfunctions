# Copyright (C) 2007-2012 LuaDist.
# Created by David Manura
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( boostmathspecialfunctions CXX )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

# Find Boost headers (only headers required -- does not need to be compiled)
#FIND_PACKAGE (Boost REQUIRED)
set ( Boost_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR} )
include_directories ( ${Boost_INCLUDE_DIR} )

# Build
install_lua_module ( special_functions src/special_functions )

# Install all files and documentation
install_doc ( doc/ )
install_test ( tests/ )
install_data ( README COPYRIGHT )
