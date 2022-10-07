cmake_minimum_required(VERSION 3.1.0)
project(test LANGUAGES CXX)

# ############################################################################## 
# Instead, append the path to the config file using the 'list' command.
list(APPEND CMAKE_PREFIX_PATH "/usr/local/lib/cmake/netCDF/")

# Look for the 'netCDFCxx' package, since that is what the config file is called.
find_package (netCDFCxx REQUIRED) 
#find_package (Eigen3 REQUIRED)

# Probably don't need this if we use the imported target below.
include_directories(
  ${NETCDF_INCLUDES}
#  ${Boost_INCLUDE_DIRS}
#  ${EIGEN3_INCLUDE_DIR} 
)

# Search all .cpp files 
file(GLOB_RECURSE SOURCE_FILES "simple_xy_wr.cpp")
file(GLOB_RECURSE SOURCE_FILES "simple_xy_rd.cpp")

add_executable(simple_xy_wr src/simple_xy_wr.cpp)
add_executable(simple_xy_rd src/simple_xy_rd.cpp)

target_link_libraries(simple_xy_wr
#  ${Boost_LIBRARIES}
#  ${EIGEN3_LIBRARIES}
  netcdf_c++4 
  netcdf
)

target_link_libraries(simple_xy_rd
#  ${Boost_LIBRARIES}
#  ${EIGEN3_LIBRARIES}
  netcdf_c++4 
  netcdf
)
