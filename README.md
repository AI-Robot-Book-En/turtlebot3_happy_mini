# TurtleBot3 Happy Mini 
## Overview
This project is based on a copy of the following TurtleBot3 repository, with the Happy Mini model (URDF and meshes) added. The mobile base parameters are the same as `waffle_pi`.  
- [ROBOTIS-GIT turtlebot3](https://github.com/ROBOTIS-GIT/turtlebot3.git)

## Additions / Changes
- turtlebot3_simulations/turtlebot3_gazebo/models/turtlebot3_happy_mini
- turtlebot3_simulations/turtlebot3_gazebo/urdf/turtlebot3_happy_mini.urdf
- turtlebot3_simulations/turtlebot3_gazebo/launch/spawn2_turtlebot3.launch.py
- turtlebot3_simulations/turtlebot3_gazebo/launch/turtlebot3_house2.launch.py

## Environment  
- ROS 2 Humble

## Installation  
- Install packages required to use Gazebo with ROS
```
$ source ~/.bashrc
$ sudo apt install ros-humble-gazebo-*
$ sudo apt install ros-humble-gazebo-ros-pkgs
```
- Install Happy Mini–related packages
```
$ cd ~/airobot_ws/src
$ git clone https://github.com/AI-Robot-Book-Humble/turtlebot3_happy_mini
$ cd ~/colcon_ws
$ colcon build 
```


## Run
1. Empty World  
![happy mini empty world](https://github.com/demulab/happy_mini_turtlebot3_sim/blob/main/happy_mini_empty_world.png "happy mini empty world")

```
$ export TURTLEBOT3_MODEL=happy_mini
$ ros2 launch turtlebot3_gazebo empty_world.launch.py
```

2. TurtleBot3 World  
![happy mini turtlebot3 world](https://github.com/demulab/happy_mini_turtlebot3_sim/blob/main/happy_mini_turtlebot3_world.png "happy mini turtlebot3 world")
```
$ export TURTLEBOT3_MODEL=happy_mini
$ ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```

3. TurtleBot3 House
![happy mini turtlebot3 house](https://github.com/demulab/happy_mini_turtlebot3_sim/blob/main/happy_mini_house.png "happy mini turtlebot3 house")
```
$ export TURTLEBOT3_MODEL=happy_mini
$ ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py
```
4. Switching the robot model
- To use Waffle Pi
```
$ export TURTLEBOT3_MODEL=waffle_pi
```

5. How to change the robot’s initial position
```
$ ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py　x_pose:=<initial_x> y_pose:=<initial_y>
```

6. How to change the robot’s initial orientation  
Use turtlebot3_house2.launch.py, which is an improved version of turtlebot3_house.launch.py that allows you to set the initial heading.  

```
$ ros2 launch turtlebot3_gazebo turtlebot3_house2.launch.py　x_pose:=<initial_x> y_pose:=<initial_y> yaw_pose:=<initial_yaw>
```

## History
- 2025-01-04: Translated the README from Japanese to English
- 2024-10-13: Initial release


## License
Apache License 2.0 license found in the LICENSE file in the root directory of this project.
