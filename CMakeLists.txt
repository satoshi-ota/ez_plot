cmake_minimum_required(VERSION 2.8.3)
project(ez_plot)
add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
)

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES ez_plot
  CATKIN_DEPENDS roscpp
  DEPENDS
)

include_directories(
 include
  ${catkin_INCLUDE_DIRS}
)

#add_library(${PROJECT_NAME}
   #src/${PROJECT_NAME}/ez_plot.cpp
#)

add_executable(test_node src/test/test.cpp)
add_dependencies(test_node ${catkin_EXPORTED_TARGETS})
target_link_libraries(test_node ${catkin_LIBRARIES})
