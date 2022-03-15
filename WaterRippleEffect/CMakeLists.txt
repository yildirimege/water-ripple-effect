cmake_minimum_required(VERSION 3.8)
message(STATUS "Using CMake Version ${CMAKE_VERSION}")

# -------------------------------------------------------------------------------------------------
# Set the C++ standard
# -------------------------------------------------------------------------------------------------
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(DEFINED ENV{VCPKG_ROOT} AND NOT DEFINED CMAKE_TOOLCHAIN_FILE)
  set(CMAKE_TOOLCHAIN_FILE "$ENV{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake"
    CACHE STRING "")
    message(" [INFO] VCPKG CMAKE_TOOLCHAIN_FILE = ${CMAKE_TOOLCHAIN_FILE}")
endif()
#
# Set vcpkg path !!!!! TO BE CHANGED!!!!
#


# -------------------------------------------------------------------------------------------------
# project settings
# -------------------------------------------------------------------------------------------------
project(WaterRippleEffect LANGUAGES CXX)

# -------------------------------------------------------------------------------------------------
# Find Libraries
# -------------------------------------------------------------------------------------------------
find_package(OpenGL REQUIRED)
find_package(GLUT)

# -------------------------------------------------------------------------------------------------
# Include Dir's'
# -------------------------------------------------------------------------------------------------
include_directories( ${OPENGL_INCLUDE_DIRS})

# -------------------------------------------------------------------------------------------------
# Link Libraries
# -------------------------------------------------------------------------------------------------
#target_link_libraries(WaterRippleEffect ${OPENGL_LIBRARIES}
					  #WaterRippleEffect PRIVATE GLUT:GLUT)



# -------------------------------------------------------------------------------------------------
# Project Definitions
# -------------------------------------------------------------------------------------------------
add_subdirectory(lib)
add_subdirectory(app)