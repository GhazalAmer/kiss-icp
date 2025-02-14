# KISS-ICP ROS wrappers

This node is just an application example on how to use the KISS-ICP C++ API. It's still considered
work in progress and we are very happy to receive any contribution from the comunity 👼

https://user-images.githubusercontent.com/21349875/214578180-b1d2431c-8fff-440e-aa6e-99a1d85989b5.mp4

## ROS2

### How to build

You should not need any extra dependency, just clone and build:

```sh
git clone https://github.com/PRBonn/kiss-icp 
colcon build
source ./install/setup.bash
```

### How to run

The only required argument to provide is the **topic name** so KISS-ICP knows which PointCloud2 to proces:

```sh
roslaunch kiss_icp odometry.launch.py bagfile:=<path_to_rosbag> topic:=<topic_name>
```

You can optionally launch the node with any bagfile, and play the bagfiles on a different shell:

```sh
roslaunch kiss_icp odometry.launch.py topic:=<topic_name>
```

and then,

```sh
rosbag play <path>*.bag
```

## ROS1

### How to build

You should not need any extra dependency, just clone and build:

```sh
cd ~/catkin_ws/
git clone https://github.com/PRBonn/kiss-icp 
catkin build
source devel/setup.bash
```

### How to run

The only required argument to provide is the **topic name** so KISS-ICP knows which PointCloud2 to proces:

```sh
roslaunch kiss_icp odometry.launch bagfile:=<path_to_rosbag> topic:=<topic_name>
```

You can optionally launch the node with any bagfile, and play the bagfiles on a different shell:

```sh
roslaunch kiss_icp odometry.launch topic:=<topic_name>
```

and then,

```sh
rosbag play <path>*.bag
```

## Out of source builds

Good news! If you don't have git or you don't need to change the core KISS-ICP library, you can just copy paste this folder into your ROS1/ROS2 workspace and build as usual. The build system will fetch the latest stable release for you.