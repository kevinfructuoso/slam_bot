# Map My World Robot SLAM Project

Udacity Robotics Software Engineer Nanodegree SLAM project repository.

For this setup, catkin_ws is the name of the active ROS workspace. If your workspace name is different, change the commands accordingly.

If you do not have an active ROS workspace, you can create one by:

```sh
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```

Clone the required repositories to the `~/catkin_ws/src` folder

```sh
cd ~/catkin_ws/src
git clone rtabmap_ros
git clone https://github.com/kevinfructuoso/slam_bot.git
```

Follow the steps to properly setup and build RTAB-map from source using this [link](https://github.com/introlab/rtabmap_ros#build-from-source)

Now install missing dependencies using rosdep install:

```sh
rosdep install -i rtabmap_ros
rosdep install -i slam_bot
```

Build the project:

```sh
cd ~/catkin_ws
catkin_make
```

Download the proper kitchen dining room `*.world` file that includes collision models required to map properly:

```sh
curl -L https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/models.tar.gz | tar zx -C ~/.gazebo/
```

Open three terminals to the `~/catkin_ws/src/slam_bot/launch` folder and run each command in one terminal:

```sh
roslaunch slam_bot world.launch world_name:=kitchen_dining.world
roslaunch slam_bot teleop.launch
roslaunch slam_bot mapping.launch
```

Begin SLAM-ing!