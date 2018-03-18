# Map My World Robot SLAM Project

Udacity Robotics Software Engineer Nanodegree SLAM project repository.

More info to come...

mkdir -p catkin_ws/src
catkin_make
source devel/setup.bash

git clone rtabmap_ros
git clone project

rosdep install -i rtabmap_ros
rosdep install -i slam_bot


follow steps for rtabmap_ros install from source - [link|https://github.com/introlab/rtabmap_ros#build-from-source]

cd catkin_ws/src/slam_bot/launch
./rtab_run

Begin SLAM-ing!