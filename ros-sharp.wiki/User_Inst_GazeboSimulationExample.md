# 1.7 [Gazebo](http://gazebosim.org/) Simulation Example Setup
**Note:** This tutorial assumes that you have completed tutorials:
* [1.1 Unity on Windows](User_Inst_Unity3DOnWindows)
* [1.2 Ubuntu on Oracle VM](User_Inst_UbuntuOnOracleVM)
* [1.3 ROS on Ubuntu](User_Inst_ROSOnUbuntu)
* [1.4 Gazebo Setup on VM](User_Inst_Gazebo)

### Setting up ROS
* Place the folder `gazebo_simulation_scene` (from [here](https://github.com/siemens/ros-sharp/tree/master/ROS)) inside the `src` folder of your Catkin workspace and rebuild your workspace.
* In the directory `gazebo_simulation_scene/scripts` make  the file `joy_to_twist.py` executable by running
```
chmod +x joy_to_twist.py
```

##### Next tutorial: [1.8 Unity Simulation Example Setup](User_Inst_UnitySimulationExample)

----
� Siemens AG, 2017-2018
Author: Suzannah Smith
(suzannah.smith@siemens.com)
