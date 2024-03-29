# follow : ROS package
a ROS package for person (step 1:color based) following + gazebo dynamic environment

## Install ROS and turtlebot3 environment


### 1. Follow the install [guide](http://emanual.robotis.com/docs/en/platform/turtlebot3/pc_setup/) for turtlebot3 PC setup.

1.1. Install Ubuntu on Remote PC.

1.2. Install ROS on Remote PC

1.3. Install turtlebot3 Dependent ROS Packages



### 2. install [turtlebot3 gazebo](http://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#turtlebot3-simulation-using-gazebo) simulation files.


### 3. update Gazebo to 7+ 
### for instructions [link](http://gazebosim.org/tutorials?cat=install&tut=install_ubuntu&ver=7.0).

```bash
sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'
wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
sudo apt-get update
sudo apt-get install gazebo7

```


### 4. add bashrc args

```bash
echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc
echo "export SVGA_VGPU10=0" >> ~/.bashrc

```

## follow package

### installing the follow package


```bash
cd ~/catkin_ws/src/
git clone https://github.com/zeged85/opencv_track3.git
cd ~/catkin_ws && catkin_make

```


## Bringup
running simulation or real robot
either run your robot with roscore, or launch the simulator.


### terminal 1 - rosCore: simulation

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



