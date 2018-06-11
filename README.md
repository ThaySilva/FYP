The Development of an Automated Rover with Image Recognition - SOAR (Sensor Operated Autonomous Rover)
======================================================================================================

Getting Started
---------------
These instructions will make for the successful deployment of the system.

__Hardware Prerequisites__

The following hardware are required before installing the SOAR software:

- Raspberry Pi 3 Model B
- Raspberry Pi Camera Module
- L298N Dual H-Bridge Motor Controller
- Radio-Controlled Car
- Genuino 101
- Grove GPS
- 2 HC-SR04

In order to connect all the hardware components, refer to section 5.3.1 on the systems official documentation.

__Software Prerequisites__

The following softwares are required in order to deploy the system:

- Xcode
- OpenCV
- TensorFlow
- Arduino IDE
- TinyGPS

To install the above software follow the respective instructions.

_Xcode_

Xcode is an IDE used for iOS development, designed and created by Apple Inc. Xcode can be downloaded from the following website:

https://developer.apple.com/xcode/

_OpenCV_

OpenCV is an open source library aimed at real-time computer vision. OpenCV can be installed in the Raspberry Pi 3 by following the steps from the link bellow:

https://www.pyimagesearch.com/2016/04/18/install-guide-raspberry-pi-3-raspbian-jessie-opencv-3/

_TensorFlow_

TensorFlow is an open source library used for machine learning applications. TensorFlow can be installed in the Raspberry Pi 3 by following these steps:

First, update the Raspberry Pi operating system:
```
    $ sudo apt-get update
```

Next, download the wheel file from this repository and install it:
```
    $ wget https://github.com/samjabrahams/tensorflow-on-raspberry-pi/releases/download/v1.1.0/tensorflow-1.1.0-cp27-none-linux_armv7l.whl
```
```
    $ sudo pip install tensorflow-1.1.0-cp27-none-linux_armv7l.whl
```

Finally, install the TFLearn API:
```
    $ sudo pip install tflearn
```

_Arduino IDE_

Arduino IDE is used to program and upload sketches to all Arduinos boards. Arduino IDE can be downloaded from the following website:

https://www.arduino.cc/en/main/software

_TinyGPS_

TinyGPS is a library that allow the data received from a GPS to be parsed. TinyGPS can be downloaded from the following website:

https://github.com/mikalhart/TinyGPS/releases/tag/v13

TinyGPS can be installed in the Genuino by following these steps on the Arduin IDE:

Sketch -> Include Library -> Add .ZIP Library


Installation
------------
The following instructions will allow for the successful deployment of each subsystem:

__RoverHQ__

_Requirements:_
- iOS Version > 8

The mobile application can be deployed on a physical iPhone or an emulator, which is provided by Xcode. Opening the file RoverHQ.xcodeproj gives full access to the code. In the FirstViewController file, the value of the variable *HOST* needs to be changed to macth the IP of the Raspberry Pi.
The RoverHQ can be deployed by selecting the physical iPhone or an emulator from the drop down list, and then clicking the run button.

__Statistics and Metrics Collector__

The statistics and metrics collector can be deployed by opening the file using the Arduino IDE. Next, the Intel Curie API needs to be installed by following these steps:

Tools -> Boards -> Boards Manager -> Intel Curie

The sketch it can then be uploaded to the Genuino board by clicking the upload button.

__Vehicle Platform__

The vehicle platform folder needs to be copied with all its contents to the Raspberry Pi. In rover_controller.py file, the value of the variable HOST needs to be changed to match the Raspberry Pi's IP addresss.

Deployment
----------
In order to deploy the system, run the rover_controller file in the Raspberry Pi with the following command:
```
    $ python rover_controller.py
```
Then run the RoverHQ mobile application to connect to it.

