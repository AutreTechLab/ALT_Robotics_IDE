cmake_minimum_required(VERSION 3.5)
project(atl_ide_interfaces)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/IDEWEBAPP.msg"
  "msg/PYTHONCODEEXECUTORSTATUS.msg"
  "msg/ATLIDESESSIONMANAGER.msg"
  "srv/IDEREGISTERROBOT.srv"
  "srv/PYTHONCODEEXECUTOR.srv"
)


ament_package()
