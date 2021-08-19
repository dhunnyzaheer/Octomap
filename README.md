# Octomap

For installation intructions, go to http://wiki.ros.org/octomap_mapping

## Using Octomap_mapping package

Go to octomap_mapping.launch file and make changes to the file where appropriate.

Use rostopic list to find topics.

Launch the octomap_mapping launch file using roslaunch.

Add Marker Array in Rviz and change the Marker topic to /occupied_cells_vis_array.

## Turtlebot3

Need to add sensor which generates point cloud data

## Husky Robot from Clearpath robotics

To make use of the octomap using the Husky, a sensor producing 3D point cloud data needs to be added. In this example, the the Husky is equipped with an Intel RealSense D435 camera. See https://www.clearpathrobotics.com/assets/guides/kinetic/husky/additional_sim_worlds.html to find out how to add the sensor. 

Open the terminal

> export HUSKY_URDF_EXTRAS=$HOME/Desktop/realsense.urdf.xacro

> roslaunch husky_gazebo husky_playpen.launch

> roslaunch octomap_server octomap_mapping.launch

> rosrun rviz rviz

Add Marker Array in Rviz and change the Marker topic to /occupied_cells_vis_array.

Add robot model 

> rosrun teleop_twist_keyboard teleop_twist_keyboard.py cmd_vel:=/husky_velocity_controller/cmd_vel

> rosrun map_server map_saver -f ~/map

![husky_robot_octomap](https://github.com/dhunnyzaheer/Octomap/blob/main/images/husky_robot_octomap.png)

## Build a map using rosbag

- Get rosbag file (In this example, I downloaded the 'freiburg2_pioneer_360' sequence from https://vision.in.tum.de/data/datasets/rgbd-dataset/download)

> roscore

- Edit octomap_mapping launch file where appropriate

- Start Octomap

> roslaunch octomap_server octomap_mapping.launch

- Open Rviz and add Markey array with topic /occupied_cells_vis_array.

> rosrun rviz rviz

- Play data

> rosbag play test.bag  --clock

![rviz_octomap_rosbag](https://github.com/dhunnyzaheer/Octomap/blob/main/images/rviz_octomap_rosbag.png)