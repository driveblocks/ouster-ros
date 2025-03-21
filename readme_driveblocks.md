# Ouster Lidar

Documentation, tutorials and further details regarding the lidar sensor and software can be found in the main README.md.

## Setup

The following documentation describes the ouster lidar driver setup on a Ubuntu workstation.

### Install the Ros2 driver

The installation procedure is described in the main README of this repo.
Keep in mind to install the driver for your specific ros distro.

### Connect via LAN

1. If you connect to the ouster Lidar via LAN, change the Ubuntu network settings to `Link-Local only` under the `IPv4` tab. Then reconnect to the network with the toggle button.

2. Get the serial number at the top of the ouster sensor. The sensor homepage can be accessed by typing in the sensor’s address (IPv4, IPv6, or hostname) in a web browser (<http://os-XYZ.local/> where XZY is the serial number).

### Run the ROS2 node

To launch the node, run

```bash
ros2 launch ouster_ros sensor.launch.xml sensor_hostname:=<sensor host name>
```

The sensor hostname seems to be the ip address by default.
Now the ROS2 node publishes the sensor data as ROS2 messages.

### Changing the sensor IP address

You can find a tutorial [here](https://forum.ouster.at/d/63-how-i-can-assign-static-ip-to-os1) and the docs for the following commands [here]():

```bash
curl -X PUT -H "Content-Type: application/json" -d '"NEW_IP/24"' OLD_IP/api/v1/system/network/ipv4/override
curl -X PUT -H "Content-Type: application/json" -d '"NEW_IP/24"' OLD_IP/api/v1/system/network/ipv4/override
```
