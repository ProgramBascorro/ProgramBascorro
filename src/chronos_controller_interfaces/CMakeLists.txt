cmake_minimum_required(VERSION 3.8)
project(chronos_controller_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)

# Generate messages and services
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/SyncWriteItem.msg"
  "msg/JointCtrlModule.msg"
  "msg/StatusMsg.msg"
  "msg/WriteControlTable.msg"
  "srv/GetJointModule.srv"
  "srv/SetJointModule.srv"
  "srv/SetModule.srv"
  "srv/LoadOffset.srv"
  DEPENDENCIES std_msgs sensor_msgs
)

ament_export_dependencies(rosidl_default_runtime std_msgs sensor_msgs)

ament_package()
