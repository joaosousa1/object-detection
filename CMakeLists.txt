cmake_minimum_required(VERSION 3.10)
project(YoloX_Demo)

# Define C++17 (requirement for mordern OpenCV)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Fins OpenCV 
find_package(OpenCV REQUIRED)

# Include headers
include_directories(${OpenCV_INCLUDE_DIRS})

# Create exec
add_executable(obj_detection_app main.cpp)

# Link libs OpenCV (core, dnn, highgui, imgproc, etc)
target_link_libraries(obj_detection_app ${OpenCV_LIBS})
