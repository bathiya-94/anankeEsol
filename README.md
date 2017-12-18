# Ananke IoT Platform



Ananke is developed by Effective Solutions Pvt Ltd as an end to end cloud based IoT platform. Ananke delivers amazing set of features for IoT developers which enable connecting IoT hardwares, applications and services together. Ananke follows platform as a service model with following features,

*Multi-protocol support (MQTT,Web Sockets and HTTP)

*Cloud services for Machine Learning and Logic Processing

*Cloud APIs for Smart Transportation, Health Care, etc

*Easy prototyping with complete graphical programming interface.

*SDK availability for Raspberry Pi, Arduino and other iot enabled developer kits

# Ananke SDK 1.0.0v
The purpose of this SDK is to connect Raspberry Pi devices to Ananke platform. Ananke recognizes a device with following parameters (please refer the Ananke User Manual to learn more).

*Device Username

*Device Password

*Device App Id

*Device Group Id

*Device Id

The SDK enable you to simply connect your device to Ananke with the above parameters. The communication with the platform is handled by the events for connection initiation, message receiving and a simple method to send messages to the platform. You can connect your device to many other internet of things using the routing layer.


# Installation

Open your terminal and navigate to the project folder.Make  sure that you have npm installed in your computer. Then type the following command in your terminal:


```
$pip install anankeesol
```
# Usage

To begin the connection:
```
sdk = anankeesol.anankeesol.Ananke()
sdk.begin(onConnect, onMessage, username, password, appId, deviceId, groupID)


```
To send a message:

```
sdk = anankeesol.anankeesol.Ananke()
sdk.send_message('This is a test program');
```

# Sample Code

```
import anankeesol
import time

sdk = anankeesol.anankeesol.Ananke()

def onConnect(status):
   if status:
       print 'connected'
   else:
       print 'not connected'


def onMessage(message):
   print "message : " + message

file=open("registration.txt","r")
file=json.load(file)


sdk.begin(onConnect, onMessage, username, password, appId, deviceId, groupId)

while True:

   time.sleep(1)
   sdk.sendMessage('This is a test program');

```




