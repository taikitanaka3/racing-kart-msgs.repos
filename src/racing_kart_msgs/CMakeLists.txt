cmake_minimum_required(VERSION 3.8)
project(racing_kart_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# Generate messages
find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/RawGnss.msg"
  "msg/RawImu.msg"
  "msg/VcuStatus.msg"
  "msg/VcuCommand.msg"
  "msg/BrakeCommand.msg"
  "msg/BrakeStatus.msg"
  "msg/SteerCommand.msg"
  "msg/SteerStatus.msg"
  "msg/VehicleDebug.msg"
  DEPENDENCIES
    "builtin_interfaces"
    "std_msgs"
    "geometry_msgs"
  ADD_LINTER_TESTS
)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

ament_auto_package()
