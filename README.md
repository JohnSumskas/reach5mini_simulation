# reach5mini_simulation
Simulation Files for the Reach 5 mini

To launch the gazebo simulation:
```
roslaunch reach5mini_simulation r5m_gazebo.launch
```

To configure move the arm publish to the `/arm_controller/command` topic using:
```
rostopic pub -1 arm_controller/command std_msgs/Float64MultiArray "layout:
  dim:
  - label: ''
    size: 0
    stride: 0
  data_offset: 0
data: [0,1,1,1,1,1]"
```
Joint order is described as:\
<jaw1, jaw2, wrist, arm_joint1, arm_joint2, base_joint>.\
\
The joints propagate from the end of the arm to the base with first 2 joints relating to the each side of the jaw. Please note that this is different to real implementation as the jaw is actuated by a linear actuator.
