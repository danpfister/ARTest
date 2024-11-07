# ARTest
Tracking a dodecahedron with aruco markers.  

## Prerequisites

Make sure to download, build and install OpenCV and OpenCV contributions beforehand. Consult ChatGPT if help is required 😉

## Build

First create a build directory
```bash
mkdir build && cd build
```

Generate build files
```bash
cmake .
```
Compile the project
```bash
make 
```

## Run

Run the executable from within the build directory and pass the video file path as argument
```bash
./ARTest path/to/video.mp4
```

or take the webcam as video source
```bash
./ARTest 0
```

*Note*: for suitable sample video visit http://media.ee.ntu.edu.tw/research/DodecaPen/

## TODO:
Update `CameraCalibration.cpp`, e.g. define the variable `root`, in order to calibrate the camera correctly.

Afterwards we can uncomment and make use of line 28 of `main.cpp`:

```cpp
CameraCalibration cc;
//cc.calibrateCamera();
```
