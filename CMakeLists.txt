cmake_minimum_required(VERSION 3.10)

# Set the project name
project(ARTest)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find required packages
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

find_package(OpenGL REQUIRED)
include_directories(${OPENGL_INCLUDE_DIRS})

find_package(glm REQUIRED)  # Still keep this to locate GLM

# Define source files (in the ARTest directory)
set(SOURCES
    ARTest/CameraCalibration.cpp
    #ARTest/Dodecahedron.cpp
    #ARTest/Graphics.cpp
    ARTest/main.cpp
    ARTest/Markers.cpp
    #ARTest/openglmain.cpp
    ARTest/PoseEstimation.cpp
    ARTest/Tools.cpp
)

# Define header files (in the ARTest directory)
set(HEADERS
    ARTest/Camera.h
    ARTest/CameraCalibration.hpp
    #ARTest/Dodecahedron.hpp
    #ARTest/Graphics.hpp
    ARTest/Markers.hpp
    ARTest/PoseEstimation.hpp
    ARTest/Shader.h
    ARTest/Tools.hpp
)

# Add the executable target
add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})

# Link other necessary libraries, but not GLM
target_link_libraries(${PROJECT_NAME} PRIVATE ${OpenCV_LIBS} ${OPENGL_LIBRARIES})

# Include GLM headers
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/ARTest ${glm_INCLUDE_DIRS})
