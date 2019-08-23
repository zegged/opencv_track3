# follow : ROS package
a ROS package for color based following

## Installation


### 1. Follow the install [guide](http://emanual.robotis.com/docs/en/platform/turtlebot3/pc_setup/) for turtlebot3 PC setup.

1.1. Install Ubuntu on Remote PC.

1.2. Install ROS on Remote PC

1.3. Install turtlebot3 Dependent ROS Packages



### 2. install [gazebo](http://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#turtlebot3-simulation-using-gazebo) from turtlebot3 PC setup guide.


## environment

```bash
echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc
echo "export SVGA_VGPU10=0" >> ~/.bashrc

```



## Setup


```bash
cd ~/catkin_ws/src/
git clone https://github.com/zeged85/opencv_track3.git
cd ~/catkin_ws && catkin_make

```


## Bringup
run simulation or real robot

### terminal 1 - rosCore: simulator or robot
run normal robot bringup with roscore, or simulator.

simulator
```bash
roslaunch follow follow_sim.launch 
```

roscore + robot launch(on robot)
```bash
roscore
```
### terminal 1.1 - teleop

```bash
roslaunch follow linear_teleop_key.launch
```





### terminal 2 - Control

launch controller
```bash
roscd follow
cd src
python ./follow3.py
```

### terminal 3 - GUI

launch GUI

```bash
roscd follow
cd src
python ./auto_ros_commands.py 
```



make sure topics match in follow3.py and auto_ros_commands.py to robot/simulator



