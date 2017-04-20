# Install_ROS_hector_quadrotor_package_steps

## Install hector_quadrotor package

sudo apt-get update

sudo apt-get install ros-indigo-hector-quadrotor-demo

cd ~/catkin_ws/src

mkdir hector_quadrotor_tutorial

cd ~/catkin_ws/src/hector_quadrotor_tutorial

wstool init src https://raw.github.com/tu-darmstadt-ros-pkg/hector_quadrotor/indigo-devel/tutorials.rosinstall

cd ~/catkin_ws

catkin_make

roslaunch hector_quadrotor_demo outdoor_flight_gazebo.launch

## Move the quadrotor

rostopic pub -1 /cmd_vel geometry_msgs/Twist -- '[0.0, 0.0, 0.2]' '[0.0, 0.0, 0.0]'

or

roscd turtlebot_teleop/launch

gedit keyboard_teleop.launch

modify the following line: "remap from ="turtlebot_teleop_keyboard/cmd_vel" to="/cmd_vel"/"

roslaunch turtlebot_teleop keyboard_teleop.launch
