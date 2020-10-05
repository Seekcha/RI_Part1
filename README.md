# RI_Part1

This Repository cotain only Part 1 of the project.
1) urdf_quad contain the details about the robot Quad (only one leg).
2) udm_oneleg_moveit is generated with moveit.
3) udm_project_control consist of node to control the robot direct or inverse.

## Installation
The package need to be install in your catkin workspace.
```
cd catkin_ws/src
git clone https://github.com/Seekcha/RI_Part1.git
catkin build
cd ..
source devel/setup.bash
```

## Execution
### Front left leg in RVIZ
Open front left leg in RVIZ in first terminal:
```
source devel/setup.bash
roslaunch udm_oneleg_moveit demo.launch
```

#### Direct Movement
Launch direct.launch in second terminal:
```
source devel/setup.bash
roslaunch udm_project_control direct.launch
```
**Calling function**
Launch in third terminal:
```
source devel/setup.bash
rosservice call /direct_kin_service_front_left_leg "
joint1:
 data: 0.7100
joint2:
 data: 0.0
joint3:
 data: 0.0
joint4:
 data: 0.0
 "
```

#### Indirect Movement
Launch indirect.launch in third terminal:
```
source devel/setup.bash
roslaunch udm_project_control direct.launch
```
**Calling function**

Launch in third terminal:
```
source devel/setup.bash
rosservice call /indirect_kin_service_legmr "
pose:
 orientation:
  w: 1
 position:
  x: 0.01
 position:
  y: 0.2
 position:
  z: -0.01
  "
```
