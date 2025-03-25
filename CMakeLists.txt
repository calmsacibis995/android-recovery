cmake_minimum_required(VERSION 3.8.2)
project(recovery VERSION 3.0)

#--------------------------------------------------------------
# Options
#
set(CMAKE_MACOSX_RPATH ON)

# use, i.e. don't skip the full RPATH for the build tree
set(CMAKE_SKIP_BUILD_RPATH  FALSE)

# when building, don't use the install RPATH already
# (but later on when installing)
set(CMAKE_BUILD_WITH_INSTALL_RPATH FALSE)

# the RPATH to be used when installing
set(CMAKE_INSTALL_RPATH "") # "

# don't add the automatically determined parts of the RPATH
# which point to directories outside the build tree to the install RPATH
set(CMAKE_INSTALL_RPATH_USE_LINK_PATH FALSE)

# enable C, C++, assembly
enable_language(C CXX ASM)

#--------------------------------------------------------------
# Dependencies
#
find_package(ZLIB REQUIRED)				# zlib

#--------------------------------------------------------------
# libpng options
# TODO: Add libpng 1.2 to source tree to be built as a static library
# that links to the final binary.
#
set(PNG_SHARED ON CACHE BOOL "" FORCE)
set(PNG_STATIC OFF CACHE BOOL "" FORCE)
set(PNG_EXECUTABLES OFF CACHE BOOL "" FORCE)	# we only want lib
set(PNG_TESTS OFF CACHE BOOL "" FORCE)		# we only want lib
set(SKIP_INSTALL_ALL OFF CACHE BOOL "" FORCE)	# we only want lib

#--------------------------------------------------------------
# Build flags.
#
if(NOT CMAKE_BUILD_TYPE)
	set(CMAKE_BUILD_TYPE Debug)
endif()

#--------------------------------------------------------------
# Subdirectories
#
include_directories(include)
add_subdirectory(lib)
add_subdirectory(src)
