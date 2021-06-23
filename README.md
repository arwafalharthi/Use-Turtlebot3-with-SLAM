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
![gazeboslam](https://user-images.githubusercontent.com/85634104/122987979-e7fd4100-d3a9-11eb-9d28-f69b13f95f75.png)

#### Run SLAM Node
in new terminal:
```
$ export TURTLEBOT3_MODEL=waffle_pi
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
![rvizturtlebot3](https://user-images.githubusercontent.com/85634104/123177648-53b8da00-d48e-11eb-86d6-b8ba1432607d.png)


#### TO control the robot
in new terminal:
```
$ export TURTLEBOT3_MODEL=waffle_pi
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
map is created

![rvizmap](https://user-images.githubusercontent.com/85634104/123177629-4ef42600-d48e-11eb-96fc-eb01c5ffe5ca.png)

now we save the map, in new terminal:
```
rosrun map_server map_saver -f ~/map
```
![savemap](https://user-images.githubusercontent.com/85634104/123178187-5a941c80-d48f-11eb-85e6-2d8d03f693b7.png)

