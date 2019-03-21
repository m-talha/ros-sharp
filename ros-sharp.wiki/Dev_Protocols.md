# RosBridgeClient Protocols

[RosBridgeClient](https://github.com/siemens/ros-sharp/tree/master/Libraries/RosBridgeClient)
is designed to keep the communication protocol generic.
New protocols can be added by implementing a simple and minimalistic
[IProtocol](https://github.com/siemens/ros-sharp/tree//master/Libraries/RosBridgeClient/Protocols/IProtocol.cs) interface:
```
public interface IProtocol
{
    void Connect();
    void Close();
    bool IsAlive();
    void Send(byte[] data);
    event EventHandler OnReceive;
}
```

A ```RosSocket``` is instantiated by passing in the
[IProtocol](https://github.com/siemens/ros-sharp/tree//master/Libraries/RosBridgeClient/Protocols/IProtocol.cs)
interface implementation that you want to use.

Example:
```
string uri = "ws://xxx.xxx.xxx.xxx:9090";
RosSocket rosSocket = new RosSocket(new RosBridgeClient.Protocols.WebSocketNetProtocol(uri));
```

Though ROS# currently comes with two WebSocket-based `IProtocol` implementations,
note that an `IProtocol` does not necessarily need to be a WebSocket client.

## Currently existing `IProtocol` interface implementations:

### 1. [WebSocketNetProtocol](https://github.com/siemens/ros-sharp/tree//master/Libraries/RosBridgeClient/Protocols/WebSocketNetProtocol.cs)

A  WebSocket client that is based on the [.NET ClientWebSocket class](https://msdn.microsoft.com/library/system.net.websockets.clientwebsocket.aspx).
* available since .NET Framework 4.5 only
* requires Windows 8 and above

### 2. [WebSocketSharpProtocol](https://github.com/siemens/ros-sharp/tree//master/Libraries/RosBridgeClient/Protocols/WebSocketSharpProtocol.cs)

A wrapper for [websocket-sharp](https://github.com/sta/websocket-sharp).
* the original  WebSocket client used in ROS#
* requires additional assembly `websocket-sharp.dll`
* not compatible with e.g. UWP

### 3. [WebSocketUWPProtocol](https://github.com/dwhit/ros-sharp/blob/WebSocketUWP/Libraries/RosBridgeClient/Protocols/WebSocketUWPProtocol.cs)

A  WebSocket client for UWP using [Windows.NetWorking.Sockets](https://docs.microsoft.com/de-de/windows/uwp/networking/websockets).
* a running ROS# version with this protocol is hosted on [@dwhit 's fork](https://github.com/dwhit/ros-sharp/tree/WebSocketUWP/).

## Platform Compatibility Overview:

| Platform | WebSocketNetProtocol | WebSocketSharpProtocol | WebSocketUWPProtocol |
|---|:-:|:-:|:-:|
| Windows 7  | no   | yes  | no   |
| Windows 8+ | yes  | yes  | no   |
| Ubuntu     | ?    | yes  | no   |
| UWP        | no   | no   | yes  |
| iOS        | ?    | yes  | no  |

If you tested a protocol on a new platform,
and can contribute with new info in above table, please do!

----
© Siemens AG, 2017-2018
Author: Dr. Martin Bischoff (martin.bischoff@siemens.com)
