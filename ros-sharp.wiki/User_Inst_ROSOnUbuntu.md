# 1.3 [ROS](http://www.ros.org/) on Ubuntu
**Note:** This tutorial assumes that you have completed tutorial:
* [1.2 Ubuntu on Oracle VM](User_Inst_UbuntuOnOracleVM)


## Setting up ROS on Ubuntu VM
* Follow [this tutorial](http://wiki.ros.org/kinetic/Installation/Ubuntu) to install [ROS](http://www.ros.org/) Kinetic
* Follow [this tutorial](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment) to install and configure the  [ROS](http://www.ros.org/) environment
* Install `rosbridge-suite` via
```
$ sudo apt-get install ros-kinetic-rosbridge-server
```
* Place the [file_server](https://github.com/siemens/ros-sharp/tree/master/ROS/file_server) package in the `src` folder of your Catkin workspace, then build by running `$ catkin_make` from the root folder of your catkin workspace. (Your catkin workspace is found in the home directory of the Ubuntu VM, and is usually called catkin_ws).

See http://wiki.ros.org/rosbridge_suite for further information.


##### Next tutorial: [1.4 Gazebo Setup on VM](User_Inst_Gazebo)

----
© Siemens AG, 2017-2018
Author: Verena Röhrl
(verena.roehrl@siemens.com)
