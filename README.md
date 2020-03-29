# Robotic Arms

## Dependencies

```sh
sudo apt-get update
sudo apt-get install ros-kinetic-controller-manager
```

Install dependencies for a package

```shell script
$ source devel/setup.bash
$ rosdep check <package_name>
$ rosdep install -i <package name>
```

If all dependencies have been installed correctly, you should be able to see

```
Output: All system dependencies have been satisfied.
```

## Run

Make sure to deactivate your Anaconda environment if it is activated!!!

### Simple arm project

```sh
$ cd /home/workspace/catkin_ws/
$ catkin_make
$ source devel/setup.bash
$ roslaunch simple_arm robot_spawn.launch
```

To suppress the warning, modify `urdf/simple_arm.gazebo.xacro`:

```
  <!-- ros_control plugin -->
  <gazebo>
    <plugin name="gazebo_ros_control" filename="libgazebo_ros_control.so">
      <robotNamespace>/simple_arm</robotNamespace>
      <robotSimType>gazebo_ros_control/DefaultRobotHWSim</robotSimType>
      <legacyModeNS>true</legacyModeNS>    <--- Add this line
    </plugin>
  </gazebo>
```
