cmake_minimum_required(VERSION 3.5)

project(ethercat_grant)



if(NOT CMAKE_CXX_STANDARD)

  set(CMAKE_CXX_STANDARD 14)

endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")

  add_compile_options(-Wall -Wextra -Wpedantic)

endif()



find_package(ament_cmake REQUIRED)

find_package(rclcpp REQUIRED)

find_library(libcap REQUIRED)



include_directories(include)

add_executable(ethercat_grant src/ethercat_grant.cpp)

target_link_libraries(ethercat_grant cap )



install(TARGETS ethercat_grant

   DESTINATION bin/${PROJECT_NAME})

ament_package()