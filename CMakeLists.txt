cmake_minimum_required(VERSION 2.8)
project(ParMETIS C)

find_package(MPI REQUIRED)

add_subdirectory(ThirdParty/gklib)
add_subdirectory(ThirdParty/metis)

# Prepare libraries.
if(SHARED)
  set(ParMETIS_LIBRARY_TYPE SHARED)
else()
  set(ParMETIS_LIBRARY_TYPE STATIC)
endif()

include(./conf/gkbuild.cmake)

include_directories(include)

# List of directories that cmake will look for CMakeLists.txt
add_subdirectory(include)
add_subdirectory(libparmetis)
add_subdirectory(programs)

