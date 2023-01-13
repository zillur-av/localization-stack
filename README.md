# localization-stack
This ROS Package is for robot localization. When we have more than one localizatin sensor in our robot, we can fuse them to get a better odometry data. For sensor fusion, we use extended kalman filter. 
To use this package, you need any two of the following ROS messages:
``` 1.nav_msgs/Odometry  2.geometry_msgs/TwistWithCovarianceStamped 3.sensor_msgs/IMU 4.geometry_msgs/PoseWithCovarianceStamped ```

We can fuse any two messages and will get a better odometry message as output.

# Implementation Details:

First, install the package using "sudo apt install ros-$ROS_DISTRO-robot-localization". We will use Gazebo Husky Robot Simulation. In this simulation, we will have a 4 wheel robot equipped with wheel encoder, IMU, GPS, and a LiDAR. 

To install the Husky robot, run the following commands.

```sudo apt-get install ros-$RIS_DISTRO-husky-simulator```

Add the following line in your bashrc file.

```export HUSKY_GAZEBO_DESCRIPTION=$(rospack find husky_gazebo)/urdf/description.gazebo.xacro```
Connect a Logitech Gamepad F710 to your computer. We will use the joystick to control the robot. Then run the following commands too:

``` 
source ~/.bashrc 
roslaunch husky_gazebo husky_playpen.launch
```
You will see gazebo simulator starts along with all required plugins. You can find all the published topics from gazebo through ```rostopic list``` and see we have IMU messages published in ```/imu/data``` topic.
