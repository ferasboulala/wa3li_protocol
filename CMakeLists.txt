cmake_minimum_required(VERSION 3.8)
project(wa3li_protocol)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
    "srv/GetLed.srv"
    "srv/SetLed.srv"
    "srv/GetTilt.srv"
    "srv/SetTilt.srv"
    "msg/KobukiBasicSideData.msg"
    "msg/KobukiBasicData.msg"
)
ament_export_dependencies(rosidl_default_runtime)

ament_package()
