# Use-Turtlebot3-with-SLAM

Install Dependent ROS 1 Packages
```
$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
```
Install TurtleBot3 Packages
```
$ sudo apt-get install ros-melodic-dynamixel-sdk
$ sudo apt-get install ros-melodic-turtlebot3-msgs
$ sudo apt-get install ros-melodic-turtlebot3
```
#### Set TurtleBot3 Model Name
TurtleBot3 Waffle Pi
```
$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc
```
#### Gazebo Simulation
Install Simulation Package
```
$ cd ~/catkin_ws/src/
$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make
```
#### Launch Simulation World
TurtleBot3 World
```
$ export TURTLEBOT3_MODEL=waffle_pi
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
to Operate TurtleBot3 ,in new terminal:
```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
![gazeboslam](https://user-images.githubusercontent.com/85634104/122987979-e7fd4100-d3a9-11eb-9d28-f69b13f95f75.png)
