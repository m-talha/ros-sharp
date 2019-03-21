# How to add new Message Types

## Option 1: Generate Message Types in Unity

* Via the `RosBridgeClient > Generate Messages` menu.

The following editor window creates action messages which are used in [actionlib tutorials](http://wiki.ros.org/actionlib_tutorials/Tutorials/SimpleActionServer%28ExecuteCallbackMethod%29) .
![](https://raw.githubusercontent.com/wiki/siemens/ros-sharp/img/Dev_NewMessageTypes_example.png)



## Option 2: Generate Messages in the RosbridgeClient Library

### 1. Declare a new message type

Add a new class in [`Libraries\RosBridgeClient\Messages`](https://github.com/siemens/ros-sharp/tree/master/Libraries/RosBridgeClient/Messages) or any of its subfolders, and make it extend the [Message](https://github.com/siemens/ros-sharp/blob/master/RosBridgeClient/Message.cs) class.

```
using Newtonsoft.Json;

namespace RosSharp.RosBridgeClient.Messages.Standard
{
    public class Float32 : Message
    {
        [JsonIgnore]
        public const string RosMessageName = "std_msgs/Float32";
        public float data;

        public Float32()
        {
            data = 0;
        }
    }
}
```

### 2. Build [RosSharp.sln](https://github.com/siemens/ros-sharp/blob/master/Libraries) in Visual Studio

* Open [`Libraries\RosSharp.sln`](https://github.com/siemens/ros-sharp/blob/master/Libraries) in Visual Studio
* In _Build_ > _Configuration Manager_ select:
    * Active Solution Configuration: __Release__
    * Active Solution Platform: __Any CPU__
* Click _Build_ > __Build Solution__

### 3. Update [RosBridgeClient.dll](https://github.com/siemens/ros-sharp/blob/master/Unity3D/Assets/RosSharp/Plugins/RosBridgeClient.dll) in your Unity Project
Copy `RosBridgeClient.dll`
* from `..Libraries\RosBridgeClient\bin\Release\`
* to `...\Unity3D\Assets\RosSharp\Plugins\`

### 4. Use the new MessageType in your Unity Project

Create a new script in [`Assets\RosSharp\Scripts\RosCommunication`](https://github.com/siemens/ros-sharp/blob/master/Unity3D/Assets/RosSharp/Scripts/RosCommunication).

__Example Publisher Script:__
```
namespace RosSharp.RosBridgeClient
{
    public class FloatPublisher : Publisher<Messages.Standard.Float32>
    {
        public float messageData;

        private Messages.Standard.Float32 message;

        protected override void Start()
        {
            base.Start();
            InitializeMessage();
        }

        private void InitializeMessage()
        {
            message = new Messages.Standard.Float32
            {
                data = messageData
            };
        }

        private void Update()
        {
            message.data = messageData;
            Publish(message);
        }
    }
}
```
__Example Subscriber Script:__
```
namespace RosSharp.RosBridgeClient
{
    public class FloatSubscriber : Subscriber<Messages.Standard.Float32>
    {
        public float messageData;

        protected override void Start()
        {
            base.Start();
        }

        protected override void ReceiveMessage(Messages.Standard.Float32 message)
        {
            messageData = message.data;
        }
    }
}
```
----
© Siemens AG, 2017-2018
Author: Suzannah Smith (suzannah.smith@siemens.com)
