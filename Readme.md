# OpenCV simple object detection

### Setup and Install (python)
```bash
python3  -m venv venv
source venv/bin/activate
pip install numpy opencv-python
```
### Model from OpenCV huggingface page
https://huggingface.co/opencv/object_detection_yolox/blob/main/object_detection_yolox_2022nov.onnx

### Run
```bash
python3 obj_detection.py
```
---

### Setup Install (C++ Ubuntu 24.04 LTS)
```bash
sudo apt update
sudo apt install g++ cmake pkg-config libopencv-dev
```

### CMakeLists.txt
```Cmake
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
```

### Build
mkdir build
cd build
cmake ..
make -j$(nproc)

### Strip and execute
cp obj_detection_app ../
cd ..
strip obj_detection_app 
./obj_detection_app
