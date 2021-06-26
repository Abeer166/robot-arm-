# robot-arm-
1- After installing Ubuntu and install ROS on Ubuntu and i use the comand "roscore" to make sure the ros is Ready and run mastr node .
2- creat a workspace catkin that contains all packages for ros  by using catkin_make.
the command would look like this:
source /opt/ros/melodic/setup.bash
then creat and build a catkin workspace
frist Create folder by command
mkdir -p -/catkin_ws/src
then go insid the folder by command
cd ~/catkin_ws/
then creat catkin by command
catkin_make
then to esey use Ros use these command once
echo "source ~/catkin_ws/devel/setup.pash"~/.bashrc
3-then I Add the package arduino_robot_arm to src folder by command 
cd ~/catkin_ws/src
sudo apt install git
git clone https://github.com/smart-methods/arduino_robot_arm
then install all the dependencies by command
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src -r -y
sudo apt-get install ros-melodic-moveit
sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control
the compile the package
catkin_make
4- then run the join state publisher to controlling the motors by command
roslaunch robot_arm_pkg check_motors.launch
5- then I controlling the motors in simulation with gazebo by this commands
first I needed to change the permission 
cd catkin_ws/src/arduino_robot_arm/robot_arm_pkg/scripts
sudo chmod +x join_states_to_gazebo.py
to open Rviz "roslaunch robot_arm_pkg check_motors.launch
to open gazebo "roslaunch robot_arm_pkg check_motors_gazebo.launch
and to control by gazebo on join state publisher use this command
rosrun robot_arm_pkg joint_states_to_gazebo.py
![IMG_8459](https://user-images.githubusercontent.com/56722657/123521427-4a628400-d6bf-11eb-99fe-df91bd23a862.JPG)
