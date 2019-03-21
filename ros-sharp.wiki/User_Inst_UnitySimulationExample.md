# 1.8 [Unity](https://unity3d.com/) Simulation Example Setup
**Note:** This tutorial assumes that you have completed tutorials:
* [1.1 Unity on Windows](User_Inst_Unity3DOnWindows)
* [1.2 Ubuntu on Oracle VM](User_Inst_UbuntuOnOracleVM)
* [1.3 ROS on Ubuntu](User_Inst_ROSOnUbuntu)
* [1.4 Gazebo Setup on VM](User_Inst_Gazebo)

### Setting up ROS
* Make sure that you followed [tutorial 1.5](User_Inst_TurtleBot2).  
* In the Ubuntu VM, install `python-xlib` (which is required by `mouse_to_joy.py`) via
```
sudo apt install python-xlib
```
* Place the folder `unity_simulation_scene` (from [here](https://github.com/siemens/ros-sharp/tree/master/ROS)) inside the `src` folder of your Catkin workspace and rebuild your workspace.
* In the directory `unity_simulation_scene/scripts` make the file `mouse_to_joy.py` executable by running
```
chmod +x mouse_to_joy.py
```

##### Next tutorial: [2. Application examples with ROS communication](User_App_ROS_ApplicationExamplesWithROSConnection)
----
� Siemens AG, 2017-2018
Author: Suzannah Smith
(suzannah.smith@siemens.com)
