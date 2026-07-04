cmake_minimum_required(VERSION 3.16)
project(AppliedComputerVisionSelfDrivingVehicle LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(MSVC)
  add_compile_options(/W4)
else()
  add_compile_options(-Wall -Wextra -pedantic)
endif()

find_package(OpenCV REQUIRED)

#add_executable(problem6_gesture_advanced_eval src/problem6_gesture_advanced_eval.cpp)
#target_link_libraries(problem6_gesture_advanced_eval PRIVATE ${OpenCV_LIBS})

add_executable(DriveMe src/main.cpp)
target_link_libraries(DriveMe PRIVATE ${OpenCV_LIBS})

message(STATUS "OpenCV include dirs: ${OpenCV_INCLUDE_DIRS}")
message(STATUS "OpenCV libs: ${OpenCV_LIBS}")
