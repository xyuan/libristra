#~----------------------------------------------------------------------------~#
# Copyright (c) 2017 Los Alamos National Security, LLC
# All rights reserved.
#~----------------------------------------------------------------------------~#

set(embedded_HEADERS
  embed_lua.h
  embed_python.h
  
  PARENT_SCOPE # THIS NEEDS TO BE HERE
)

cinch_add_unit( ristra_lua_utils
  SOURCES test/lua_utils.cc
  INPUTS test/lua_test.lua test/mock_box_2d.lua
  LIBRARIES Ristra )

if(RISTRA_ENABLE_PYTHON)
  cinch_add_unit( ristra_python_utils 
    SOURCES test/python_utils.cc 
    INPUTS test/python_test.py
    LIBRARIES Python3::Python )
endif()

#----------------------------------------------------------------------------~-#
# Formatting options for vim.
# vim: set tabstop=2 shiftwidth=2 expandtab :
#----------------------------------------------------------------------------~-#
