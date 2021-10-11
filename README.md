# TurtleBot3
<img src="https://github.com/ROBOTIS-GIT/emanual/blob/master/assets/images/platform/turtlebot3/logo_turtlebot3.png" width="300">  

[![kinetic-devel Status](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/workflows/kinetic-devel/badge.svg)](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/tree/kinetic-devel)

[![melodic-devel Status](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/workflows/melodic-devel/badge.svg)](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/tree/melodic-devel)

[![noetic-devel Status](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/workflows/noetic-devel/badge.svg)](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/tree/noetic-devel)

[![dashing-devel Status](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/workflows/dashing-devel/badge.svg)](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/tree/dashing-devel)

[![foxy-devel Status](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/workflows/foxy-devel/badge.svg)](https://github.com/ROBOTIS-GIT/turtlebot3_simulations/tree/foxy-devel)

## Instructions for ROS 2 Foxy (Gazebo simulator)

Istall dependencies
```
sudo apt install gazebo11 ros-foxy-gazebo-ros-pkgs ros-foxy-dynamixel-sdk
```

Create workspace
```
mkdir -p ~/turtlebot3_ws/src
```

Download packages
```
cd ~/turtlebot3_ws/src
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git && cd turtlebot3_msgs/ && git checkout foxy-devel && cd ~/turtlebot3_ws/src
git clone https://github.com/ROBOTIS-GIT/turtlebot3.git && cd turtlebot3 && git checkout foxy-devel
cd ~/turtlebot3_ws && colcon build
```

Now open your `~/.bashrc` file and add optionally the following lines to setup the simulation environment:
```
# Turtlebot
alias tbotsim="source ~/turtlebot3_ws/install/setup.bash && export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:~/turtlebot3_ws/src/turtlebot3/turtlebot3_simulations/turtlebot3_gazebo/models && export TURTLEBOT3_MODEL=waffle_pi"
```

Then source the file and run the alias
```
source ~/.bashrc && tbotsim
```

Finally run the simulation
```
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```

![Simulator screenshot](./sim.png)
