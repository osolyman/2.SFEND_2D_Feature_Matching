# SFND 2D Feature Tracking

<img src="images/keypoints.png" width="820" height="248" />

The idea of the camera course is to build a collision detection system - that's the overall goal for the Final Project. As a preparation for this, you will now build the feature tracking part and test various detector / descriptor combinations to see which ones perform best. This mid-term project consists of four parts:

* First, you will focus on loading images, setting up data structures and putting everything into a ring buffer to optimize memory load. 
* Then, you will integrate several keypoint detectors such as HARRIS, FAST, BRISK and SIFT and compare them with regard to number of keypoints and speed. 
* In the next part, you will then focus on descriptor extraction and matching using brute force and also the FLANN approach we discussed in the previous lesson. 
* In the last part, once the code framework is complete, you will test the various algorithms in different combinations and compare them with regard to some performance measures. 

See the classroom instruction and code comments for more details on each of these parts. Once you are finished with this project, the keypoint matching part will be set up and you can proceed to the next lesson, where the focus is on integrating Lidar points and on object detection using deep-learning. 

## Dependencies for Running Locally
* cmake >= 2.8
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* OpenCV >= 4.1
  * This must be compiled from source using the `-D OPENCV_ENABLE_NONFREE=ON` cmake flag for testing the SIFT and SURF detectors.
  * The OpenCV 4.1.0 source code can be found [here](https://github.com/opencv/opencv/tree/4.1.0)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./2D_feature_tracking`.


# Mid-Term Project Report

## Task MP.1 Data Buffer

* Create a vector to store dataBuffer objects with a maximum size limit, such as 2 elements. Achieve this by adding new elements at one end and removing elements from the other end as necessary.

* You can find the corresponding implementation in MidTermProject_Camera_Student.cpp, specifically in lines 62 to 73.

## Task MP.2 Keypoint Detection

* Implement detectors HARRIS, FAST, BRISK, ORB, AKAZE, and SIFT and make them selectable by setting a string accordingly.

* The related implementation can be found in MidTermProject_Camera_Student.cpp lines (78 - 100) & in matching2D.cpp lines (152 - 277).

## Task MP.3 Removing keypoints

* Selecting the keypoints only on the preceding vehicle. This can be done by defining a rectangle by 4 vertaxes. then discarding any keypoints outside of this rectangle. 

* The related implementation can be found in MidTermProject_Camera_Student.cpp lines (101 - 119)

## Task MP.4 Keypoint Descriptor

* Implement descriptors and enable string-based selection based on descriptorType BRIEF, ORB, FREAK, AKAZE, SIFT.

* The related implementation can be found in MidTermProject_Camera_Student.cpp lines (146 - 153) in matching2D.cpp lines (61 - 109).

## Task MP.5 Keypoint Descriptor Matching

* Implement FLANN matching as well as k-nearest neighbor selection. Both methods must be selectable using the respective strings in the main function.

* The related implementation can be found in MidTermProject_Camera_Student.cpp lines (170 - 179) in matching2D.cpp lines (6 - 38).

## Task MP.6 Keypoint Descriptor Matching

* KNN match selection and perform descriptor distance ratio filtering with t=0.8, which looks at the ratio of best vs. second-best match to decide whether to keep an associated pair of keypoints.

* The related implementation can be found in MidTermProject_Camera_Student.cpp lines (170 - 179) in matching2D.cpp lines (39 - 59).

## Task MP.7 - MP.8 - MP.9 please see documentation.pdf file