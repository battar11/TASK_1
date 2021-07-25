<h1>TASK_1</h1>
  
  
  
<p>rinstaling Ubuntu and robot arm movement. 
First I installed virtual box to run then I took Ubuntu 16.04 from the offical website https://releases.ubuntu.com/16.04/
I suppose to use the ubuntu 18.04 and ROS melidic however, I tried many times but it didn’t work. 
following this video I was able to get my task done: https://www.youtube.com/watch?v=fr6TXEd2rXI.

  
Installing ROS:
using the terminal run these commands.
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
the above two commands to setup connection 

sudo apt-get update

apt-cache search ros-kinetic

echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

sudo apt install python-rosdep

sudo rosdep init

rosdep update

sudo apt-get install ros-noetic-catkin

mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/

catkin_make

cd ~/catkin_ws/src

git clone https://github.com/smart-methods/arduino_robot_arm.git #downloading arm package

cd ~/catkin_ws

rosdep install --from-paths src --ignore-src -r -y

sudo apt-get install ros-kinetic-moveit

sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui

sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control

sudo nano ~/.bashrc

source /home/battar/catkin_ws/devel/setup.bash
#then press (ctrl + o) to write out. Make sure in the above command you change the user as use it's my user and you should put yours.

roslaunch robot_arm_pkg check_motors.launch


</p>
