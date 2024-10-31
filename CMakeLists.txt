cmake_minimum_required(VERSION 3.8)
project(r4f_yolo)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)

add_executable(yolo_segmentation src/yolo_segmentation.cpp)
ament_target_dependencies(yolo_segmentation rclcpp std_msgs)

install(TARGETS
  yolo_segmentation
  DESTINATION lib/${PROJECT_NAME})

ament_package()
