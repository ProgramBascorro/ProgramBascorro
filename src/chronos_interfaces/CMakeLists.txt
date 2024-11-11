cmake_minimum_required(VERSION 3.8)
project(chronos_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/FootStepArray.msg"
  "msg/FootStepCommand.msg"
  "msg/JointOffsetData.msg"
  "msg/JointOffsetPositionData.msg"
  "msg/JointPose.msg"
  "msg/JointTorqueOnOff.msg"
  "msg/JointTorqueOnOffArray.msg"
  "msg/KinematicsPose.msg"
  "msg/PreviewRequest.msg"
  "msg/PreviewResponse.msg"
  "msg/StartAction.msg"
  "msg/Step2D.msg"
  "msg/Step2DArray.msg"
  "msg/WalkingParam.msg"
  "msg/WalkingParamModule.msg"
  "srv/GetJointPose.srv"
  "srv/GetKinematicsPose.srv"
  "srv/GetPresentJointOffsetData.srv"
  "srv/GetPreviewMatrix.srv"
  "srv/GetWalkingParam.srv"
  "srv/IsRunning.srv"
  "srv/SetWalkingParam.srv"
  DEPENDENCIES geometry_msgs std_msgs sensor_msgs
)

ament_export_dependencies(rosidl_default_runtime geometry_msgs std_msgs sensor_msgs)

ament_package()
