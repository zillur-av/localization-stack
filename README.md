# localization-stack
This ROS Package is for robot localization. When we have more than one localizatin sensor in our robot, we can fuse them to get a better odometry data. For sensor fusion, we use extended kalman filter. 
To use this package, you need any two of the following ROS messages:
``` 1.nav_msgs/Odometry  2.geometry_msgs/TwistWithCovarianceStamped 3.sensor_msgs/IMU 4.geometry_msgs/PoseWithCovarianceStamped ```

We can fuse any two messages and will get a better odometry message as output.
