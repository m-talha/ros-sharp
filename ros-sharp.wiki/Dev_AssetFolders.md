# ROS# Asset Folders #

The `Unity3D\Assets\RosSharp\`directory is structured as follows:

* `RosSharp`
    * `Editor`: Unity Editor-specific assets which are excluded from builds at runtime
        * `CustomEditor`: Unity menu and inspector modifications
        * `MeshImporter`: Mesh import scripts for .dae and .stl files
        * `UrdfImporter`: Unity-specific UrdfImporter class extensions
    * `Plugins`: ROS# Code created outside Unity, in particular [RosBridgeClient.dll](https://github.com/siemens/ros-sharp/tree/master/RosBridgeClient) and [UrdfImporter.dll](https://github.com/siemens/ros-sharp/tree/master/UrdfImporter)    
    * `Scenes`: Application example scenes
    * `Scripts`:   Scripts providing runtime functionalities
       * `Extensions`: Scripts containing extension methods
       * `MessageHandling`: Unity components for handling of ROS Message data
       * `RosCommunication`: Unity components for ROS communication
       * `UrdfComponents`: Unity components related to URDF model
----
© Siemens AG, 2017-2018
Author: Dr. Martin Bischoff (martin.bischoff@siemens.com)
