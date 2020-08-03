# self-driving-car-fyp

In this repository I will share the **source code** of all the projects of my Final Year Project of Self Driving Car.

--- 
## Table of Contents

#### [M1 - Detecting Lane Lines](module_1_lane_finding_basic)
 - **Summary:** Detected highway lane lines on a video stream. Used OpencV image analysis techniques to identify lines, including Hough Transforms and Canny edge detection.
 - **Keywords:** Computer Vision
 
#### [M2 - Traffic Sign Classification](module_2_traffic_sign_classifier)
 - **Summary:** Built and trained a deep neural network to classify traffic signs, using TensorFlow. Experimented with different network architectures. Performed image pre-processing and validation to guard against overfitting.
 - **Keywords:** Deep Learning, TensorFlow, Computer Vision
 
#### [M3 - Behavioral Cloning](module_3_behavioral_cloning)
 - **Summary:** Built and trained a convolutional neural network for end-to-end driving in a simulator, using TensorFlow and Keras. Used optimization techniques such as regularization and dropout to generalize the network for driving on multiple tracks.
 - **Keywords:** Deep Learning, Keras, Convolutional Neural Networks

#### [M4 - Advanced Lane Finding](module_4_advanced_lane_finding)
 - **Summary:** Built an advanced lane-finding algorithm using distortion correction, image rectification, color transforms, and gradient thresholding. Identified lane curvature and vehicle displacement. Overcame environmental challenges such as shadows and pavement changes.
 - **Keywords:** Computer Vision, OpenCV
 
#### [M5 - Vehicle Detection and Tracking](module_5_vehicle_detection)
 - **Summary:** Created a vehicle detection and tracking pipeline with OpenCV, histogram of oriented gradients (HOG), and support vector machines (SVM). Implemented the same pipeline using a deep network to perform detection. Optimized and evaluated the model on video data from a automotive camera taken during highway driving.
 - **Keywords:** Computer Vision, Deep Learning, OpenCV
 
#### [M6 - MPC Control](module_6_MPC_control)
- **Summary:** Implement an MPC controller for keeping the car on track by appropriately adjusting the steering angle. Differently from previously implemented PID controller, MPC controller has the ability to anticipate future events and can take control actions accordingly. Indeed, future time steps are taking into account while optimizing current time slot.
- **Keywords:** C++, MPC Controller

#### [M7 - Path Planning](module_7_path_planning)
- **Summary:** The goal in this project is to build a path planner that is able to create smooth, safe trajectories for the car to follow. The highway track has other vehicles, all going different speeds, but approximately obeying the 50 MPH speed limit. The car transmits its location, along with its sensor fusion data, which estimates the location of all the vehicles on the same side of the road.
- **Keywords:** C++, Path Planning

#### [M8 - Road Segmentation](module_8_road_segmentation)
- **Summary:** Implement the road segmentation using a fully-convolutional network.
- **Keywords:** Python, TensorFlow, Semantic Segmentation

### [System Integration](system-integration)
- All Modules Combined in the this project.



## Team
|  **Shivang Medhekar** | **Sohum Khot** |
| :---: |:---:|
| [![Shivang Medhekar](https://avatars2.githubusercontent.com/u/69140290?s=200&u=5df35a82b6d2b6b7b876dfdc22d451c92d30a5c6&v=4)](https://github.com/shivangmedhekar)    | [![Sohum Khot](https://avatars0.githubusercontent.com/u/49232257?s=200&u=909a1b15cee566203a07ef8859148b6c508029d2&v=4)](https://github.com/sohumkhot) |
| <a href="https://github.com/shivangmedhekar" target="_blank">`github.com/shivangmedhekar`</a> | <a href="https://github.com/sohumkhot" target="_blank">`github.com/sohumkhot`</a> |

## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
