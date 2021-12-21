## Videos
All of the videos are in the `videos` folder.


## Exercise 1
The code is in `e1.py`. There are no dependency other than basic packages. The commands to run the program are as below.

Open the 1st terminal.

    source devel/setup.bash
    roslaunch basic_launch dbw_joystick

Open the 2nd terminal.

    source devel/setup.bash
    python e1.py

## Exercise 2
The code is in `e2.py`. There is 2 dependencies called `gnss_sensor` and `yolo3`. The commands to run the program are as below.

Open the 1st terminal.

    source devel/setup.bash
    roslaunch basic_launch dbw_joystick

Open the 2nd terminal.

    source devel/setup.bash
    roslaunch basic_launch gnss_sensor_init.launch

Open the 3rd terminal.

    source devel/setup.bash
    python e2.py

## Exercise 3
There are no codes for exercise 3. There is 2 dependencies called `rosbag` and `hector_slam`. The steps to do step 3 are as below.

### Step 1. Record sensor data 
Get into the vechile and enter the workspace of the computer. Run the command below.

Open the 1st terminal.

    source devel/setup.bash
    roslaunch basic_launch dbw_joystick

Open the 2nd terminal. (exercise3.bag is also attached in the folder)

    source devel/setup.bash
    rosbag record -a -O exercise3.bag 

### Step 2. Display recorded sensor data (see ./videos/e3.MOV)
Open the 1st terminal.

    source devel/setup.bash
    roslaunch hector_slam_launch tutorial.launch

Open the 2nd terminal. (Our recorded exercise3.bag is also attached in the folder)

    source devel/setup.bash
    rosbag play exercise3.bag /lidar1/scan:=/scan -- clock


## Exercise 4
The codes are in `gem_gnss/scripts/gem_gnss_pp_tracker_pid.py`. There is 1 dependency called `gnss_sensor`. There are 2 steps to do the exercise 4.

### Step 1. Record the figure 8 path 
Get into the vechile and enter the workspace of the computer. Run the command below.

Open the 1st terminal.

    source devel/setup.bash
    roslaunch basic_launch dbw_joystick

Open the 2nd terminal.

    source devel/setup.bash
    roslaunch basic_launch gnss_sensor_init.launch

Open the 3rd terminal and let the safty driver drive the vechicle in a figure 8 path.

    source devel/setup.bash
    python ./gem_gnss/scripts/gem_gnss_pp_tracker_pid.py

### Step 2. Let the vechicle follow the figure 8 path automatically (see ./videos/e4.MOV)
Open the 1st terminal.

    source devel/setup.bash
    roslaunch basic_launch dbw_joystick

Open the 2nd terminal.

    source devel/setup.bash
    roslaunch basic_launch gnss_sensor_init.launch

Open the 3rd terminal and let the computer controls the vechicle.

    source devel/setup.bash
    python ./gem_gnss/scripts/gem_gnss_pp_tracker_pid.py

