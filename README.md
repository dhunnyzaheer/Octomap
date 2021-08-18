# Octomap

For installation intructions, go to http://wiki.ros.org/octomap_mapping

## Using Octomap_mapping package

Go to octomap_mapping.launch file and make changes to the file where appropriate.

Use rostopic list to find topics.

Launch the octomap_mapping launch file using roslaunch.

Add Marker Array in Rviz and change the Marker topic to /occupied_cells_vis_array. 

## Turtlebot3

## Husky Robot from Clearpath robotics

To make use of the octomap using the Husky, a sensor proding point cloud data needs to be added. In this example, the the Husky is equipped with an Intel RealSense D435 camera. See https://www.clearpathrobotics.com/assets/guides/kinetic/husky/additional_sim_worlds.html to find out how to add the sensor. 