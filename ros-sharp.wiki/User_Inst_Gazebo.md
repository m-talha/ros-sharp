# 1.4 [Gazebo](http://gazebosim.org/) Setup for VM
**Note:** This tutorial assumes that you have completed tutorials:
* [1.2 Ubuntu on Oracle VM](User_Inst_UbuntuOnOracleVM)
* [1.3 ROS on Ubuntu](User_Inst_ROSOnUbuntu)

This tutorial shows how to install and setup [Gazebo](http://gazebosim.org/), which is used for robot simulation in [ROS](http://www.ros.org/).

 * Using the following commands, setup your Ubuntu VM to accept software from packages.osrfoundation.org and install the Gazebo7 packages.
```
$ sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'
$ wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
$ sudo apt-get update
$ sudo apt-get install gazebo7
```
 * Install the required packages
```
$ sudo apt-get install libgazebo7-*
```
 * Make sure that you now have the prefered Gazebo version. (**Note:** Due to the use of Oracle VM VirtualBox, there may occur a rendering issue with [Gazebo](http://gazebosim.org/). In order to avoid this, we use [Gazebo](http://gazebosim.org/) version 7.x.x.)
```
$ gazebo --version
```

**Note:** Visit the [gazebosim](http://gazebosim.org/tutorials/?tut=ros_wrapper_versions) webpage and its [tutorial](http://gazebosim.org/tutorials?tut=install_ubuntu) page for more details.

##### Next tutorial: [1.5 TurtleBot2](User_Inst_TurtleBot2)

----
© Siemens AG, 2018
Author: Berkay Alp Cakal (berkay_alp.cakal.ct@siemens.com)
