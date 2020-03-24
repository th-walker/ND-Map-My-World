# Map My World - Robotics Project - Udacity Robotics Engineer ND
## Overview
The objective of the project is to create a 2D occupancy grid and 3D octomap from a simulated environment using a custom robot with the RTAB-Map package.

RTAB-Map (Real-Time Appearance-Based Mapping) is a popular solution for SLAM to develop robots that can map environments in 3D. RTAB-Map has good speed and memory management, and it provides custom developed tools for information analysis. The quality of documentation for RTAB-Map on ROS Wiki is quite high also. 
For this project `rtabmap_ros` package (a ROS wrapper (API) for interacting with RTAB-Map) will be used.

## Instructions

Project was developed with the following methodolodgy.
1. Developed package to interface with `rtabmap_ros` package
2. Built upon localisation project to make necessary changes to interface the robot with RTAB-Map.
3. Ensured that all files are in appropriate places, links are properly connected, naming is properly setup and topics are correctly mapped. 
4. Launched robot and `teleop` around the room to generate a proper map of the environment

## Running Model

Launch the world in Gazebo:
```
catkin_make
source devel/setup.bash
roslaunch my_robot world.launch
```

Launch the teleop node for keyboard control of robot:
```
source devel/setup.bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

Launch the RTAB-Map mapping node
```
source devel/setup.bash
roslaunch my_robot mapping.launch
```

## RTAB-Map Visualisation Tools Database Viewer

After completing mapping of environment, usually three passes are needed for good results, stop mapping.launch.
Run the following command to view the map generated:

```
rtabmap-databaseViewer ~/.ros/rtabmap.db
```
