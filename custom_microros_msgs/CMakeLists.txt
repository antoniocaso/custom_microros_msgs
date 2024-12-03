cmake_minimum_required(VERSION 3.5)
project(custom_microros_msgs)
#set(BUILD_SHARED_LIBS OFF)
if(CMAKE_TOOLCHAIN_FILE)
    include(${CMAKE_TOOLCHAIN_FILE})
endif()
message(STATUS "C Compiler: ${CMAKE_C_COMPILER}")
message(STATUS "C Flags: ${CMAKE_C_FLAGS}")

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

set(msg_files
  "msg/StmToUbuntuMessage.msg"
  "msg/UbuntuToStm32Arbiter.msg"
  "msg/UbuntuToStm32Info.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()

