# Group 5: Homework 3 Part 2 README

Authors (Alphabetical): Nader Ahmed, Demiana Barsoum, Shail Dalal, Fiona Neylon, Courtney Smith

This packages details the work done by Group 5 for creating a Wrapper class for the Emika Franka Panda robots to plan and execute motion trajectories. The wrapper class is called `frankastein.py` and is located in the `mattagascar` package. This file import the `populate_msgs.py` file which contains the PopulateMsgs class. This class is responsible for getting and setting the required messages for the class. The wrapper class was tested using the `iliketomoveitmoveit.py` test node. 

### Usage Instructions
To use this class, import at the top of the file of your node `from mattagascar.submodules.frankastein import *`. Then, create an instance of the class `self.KingJulien = Wrapper(self, robot_type='panda_manipulator')`. The `robot_type` argument is to determine the type of robot you are using. The default is `panda_manipulator`. 

### cb_joint_state method
This method is a callback function for the joint states of the robot. It is called when the robot publishes its joint states.

### plan_path_to_position
This method is used to plan a path to a position. It takes in the position as a list of floats and calls the inverse kinematics Action Server to plan a path to that position and returns the future object.

### plan_path_to_orientation
This method is used to plan a path to an orientation. It takes in the orientation as a list of floats and calls the inverse kinematics Action Server to plan a path to that orientation and returns the future object.

### plan_path_to_position_orientation
This method is used to plan a path to a position and orientation. It takes in the position and orientation as a list of floats and calls the inverse kinematics Action Server to plan a path to that position and orientation and returns the future object.

### add_box
This method is used to add a box to the planning scene. It takes in the dimensions of the box and the position of the box. It then calls the planning scene to add the box to the planning scene.

### Using Wrapper with the test node in Rviz
1. Use `ros2 launch ros2 launch franka_moveit_config moveit.launch.py robot_ip:=dont-care use_fake_hardware:=true load_gripper:=true` to launch the panda robot before running the test node for the planning and executing trajectories.

2. Use `ros2 run mattagascar iliketomoveitmoveit` to test the Wrapper `frankastein.py`.

### File Structure
<pre>
|--homework3group-Fneylon/   (Git Repository)
    |--mattagascar           (Package)
        |--mattagascar
            |--submodules
                |-- __init__.py
                |-- frankastein.py  (Wrapper)
                |-- populate_msgs.py (Helper Functions)
            |--__init__.py
            |--iliketomoveitmoveit.py (Test Node)
        |--resource
        |--test
        |--package.xml
        |--setup.cfg
        |--setup.py
    |--README.md
    |--.gitignore
    |--citations.txt
</pre>