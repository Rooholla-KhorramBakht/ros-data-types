# ROS Data Types

This repository contains a rich set of ROS data types in
[OMG IDL](https://www.omg.org/spec/IDL) format. These types enable you to
create native DDS applications capable of interoperating with ROS 2
applications using the equivalent
[common interfaces](https://github.com/ros2/common_interfaces).

ROS data types are organized in different modules, including both
general-purpose types (e.g., `std_msgs`) and domain-specific types (e.g.,
`trajectory_msgs`).

```bash
ros-data-types/
├── diagnostic_msgs
├── gazebo_msgs
├── geometry_msgs
├── lifecycle_msgs
├── nav_msgs
├── pendulum_msgs
├── sensor_msgs
├── shape_msgs
├── std_msgs
├── stereo_msgs
├── test_msgs
├── tf2_msgs
├── trajectory_msgs
└── visualization_msgs
```

For more information on the original ROS 2 common interfaces, please refer to
this [repository](https://github.com/ros2/common_interfaces).

This repository also includes data type definitions for topics that are *ROS2 internal*, 
for supporting ROS2 parameters, actions, RCL and RMW, etc., thus enabling non-ROS2 
Connext DDS applications full access and interoperability with any ROS2 component, 
module, tool, visualizer, etc.


## Building ROS Type Library

To make the messages types using the Cylcone DDS compiler, first install the cyclone-DDS:
```bash
pip install cyclone-dds
```
Clone the repository:

```bash
cd /path/to/workspace
git clone https://github.com/Rooholla-KhorramBakht/ros-data-types.git
cd ros-date-types
```
Then use the `idlc` compiler to make the python/C definition of the messages of interest:

```bash
mkdir build && cd build
idlc -l py -I /path/to/workspace/ros-data-types  ../geometry_msgs/msg/TwistStamped.idl
```

Now you can use the generated message types in your projects!
