# 1.5 [TurtleBot2](http://www.turtlebot.com/turtlebot2/)

**Note:** This tutorial assumes that you have completed tutorials:
* [1.2 Ubuntu on Oracle VM](User_Inst_UbuntuOnOracleVM)
* [1.3 ROS on Ubuntu](User_Inst_ROSOnUbuntu)

This tutorial explains how to set up the example robot [TurtleBot2](http://www.turtlebot.com/turtlebot2/).
*  Install the required TurtleBot2 sources on the Ubuntu VM
```
$ sudo apt-get install ros-kinetic-turtlebot ros-kinetic-turtlebot-apps ros-kinetic-turtlebot-interactions ros-kinetic-turtlebot-simulator ros-kinetic-kobuki-ftdi ros-kinetic-ar-track-alvar-msgs ros-kinetic-turtlebot-gazebo
```
* Set the required environment variables:

```
$ export TURTLEBOT_BASE=roomba
$ export TURTLEBOT_STACKS=circles
$ export export TURTLEBOT_3D_SENSOR=kinect
```

##### Next tutorial: [1.6 Shadow Hand](User_Inst_ShadowHand)

----
© Siemens AG, 2018
Author: Verena Röhrl
(verena.roehrl@siemens.com)