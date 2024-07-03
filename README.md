# little_slam
[Aiya Zhengyu "SLAM Getting Started" (O ー Madness)](https://www.ohmsha.co.jp/book/9784274221668/)Sample program
[LittleSLAM](https://github.com/furo-org/LittleSLAM.git)Is transplanted to ROS.

# install
```
cd ~/catkin_ws/src
git clone --recursive https://github.com/kiyoshiiriemon/little_slam
cd ~/catkin_ws/
catkin_make
``` 

# Execution method
```
rosrun little_slam little_slam_node _customize=I
```
Input
- Odometry (TF"base_link" -> "odom")
- sensor_msgs::LaserScan ("scan")

The output
- Point group map sensor_msgs::PointCloud2 ("pcmap")
- Robot trajectory nav_msgs::Path ("path")

is.

# Parameter
- customize
   - You can see the difference in behavior by switching the element technology used inside the SLAM.
   - From A to I, i is a full function implementation version that includes loop resolution (default)
   
# Limitations
 - In the current implementation, it is premised that LIDAR is attached to the center of the robot (coordinate conversion is omitted).
    - If you have a request, fix it so that you can read the conversion from TF
   
# demo
[![](https://img.youtube.com/vi/imZT1B95MiQ/0.jpg)](https://www.youtube.com/watch?v=imZT1B95MiQ)

