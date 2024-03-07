# Software Issues

**Q: Why can't my compiler find the corresponding device?**

- A: You need to set up a development environment and install the corresponding project library before you can develop the device.

## 1 About myStudio

**Q: What is myStudio?**

- A: It is self-developed software by our company. It is a tool for burning or modifying the firmware of existing robotic arms launched by our company.

**Q: Why can't the device operate normally after I burn firmware into the ATOM terminal?**

- A: The firmware of the ATOM terminal needs to use our factory firmware. Other unofficial firmware cannot be used during operation. If the device accidentally burns other firmware, you can use the "myCobot firmware burner" to select the ATOM terminal, select the serial port, and choose the ATOMMAIN firmware for burning.

**Q: Can the drag teaching in the firmware record the gripper movement?**

- A: It is temporarily impossible to use dragging and teaching to record the movement of the gripper because the gripper belongs to joint No. 7, and our dragging and teaching can only record and play back the motion of joints No. 1-6.

**Q: Why can't I still drag and teach after burning the minirobot firmware?**

- A: First, check whether the M5Stack-basic firmware and Atom firmware are burned, whether the burned firmware meets the requirements to be achieved, and whether the burned firmware is the latest version.
- It is recommended to burn the minirobot firmware to version v2.1 and the top AtomMAIN firmware to v4.1 and above (need to support myStudio version v4.3.1 and above).

**Q: What should I do if mycobot’s serial port cannot be recognized on myStudio?**

- A: If your computer device does not prompt for the connected robotic arm, please install the serial port driver first.
- It should also be noted that the Raspberry Pi, Arduino, and Jetson Nano series robotic arms cannot be connected to a laptop using a data cable. You need to use myStudio to burn firmware in the built-in system.

**Q: Can the dragging teaching recording track be saved to the card?**

- A: Currently, it cannot be saved to the memory card. And dragging and teaching can only save one path at a time, and the next recording will overwrite the previous action.

## 2 About RoboFlow

**Q: Can I use RobotStudio software for programming?**

- A: Our own industrial programming software, roboFlow, can be used, but RobotStudio is from ABB and cannot communicate with us.

**Q: What is the reason why the roboFlow software quickly moves beyond the limit?**

- A: It may be that one joint or multiple joints exceed the limit.

**Q: How does roboFlow load a program that has been written?**

- A: After logging in, select program robot and click load program. Clicking run program directly cannot be used, only Pro600 can.

**Q: When using roboFlow on Pro600, the log shows 456 joints stopped. Is this normal?**

- A: This is normal.

## 3 About myCobot Phone Controller

**Q: What version of firmware should be burned into myCobot Phone Controller app?**

- A: You need to burn the Atom firmware AtomMAIN2.5 version in myStudio.
- **(As of now, the mobile APP control function has been disabled. Please pay attention to the release of myStudio firmware version information for the restart time.)**

## 4 About myBlockly

**Q: Child process exited with code 0 always appears when running myBlockly. Why?**

- A: This is not an error report. A real error report requires a detailed analysis of the specific situation. This string of characters represents the end of the program and returns the binary number 0, which represents termination.

## 5 About Arduino

**Q: An error occurred when running the Arduino program: It corresponds to multiple libraries, and the MycobotSaver.h file cannot be found.**

-A: First of all, the first error reported corresponds to multiple libraries, indicating used and unused ones. Just delete one library.
There is another error that MycobotSaver.h is not found. This is a problem with the library name. You need to change to MyCobotSaver.h.
This program may have been used before, but the file name has changed later. You can find the MyCobotSaver file, and then copy and paste the MyCobotSaver file you found into the myCobotProBasic folder.

**Q: 280arduino control method**

-A: 1. That’s right. Currently, if you use an Uno board, you really need an Arduino to control it. For these two boards, MKRWiFi1010 Mega2560, you can use Python or ROS.
2. The Uno board is connected to the Arduino board through a DuPont cable and cannot be plugged in directly.
3. Our Arduino has cases for you to use directly. I will give you the link and screenshot, and you can directly burn it into the Uno board. If you want to develop other Arduino programs by yourself, you can directly use Arduino software to compile the previous case. The tutorial is in this section.

## 6 About ROS1

**Q: When the terminal switches to ~/catkin_ws/src and uses git to install and update mycobot_ros, it appears that the target path "mycobot_ros" already exists. What is the reason?**

- A: It means that there is already a `mycobot_ros` package in `~/catkin_ws/src`. You need to delete it in advance and then perform the git operation again.

**Q: When rosrun is running, the terminal error message shows `could not open port /dev/ttyUSB0: Permission: '/dev/ttyUSB0'`. Why?**

- A: The serial port permissions are not enough. Enter `sudo chmod 777 /dev/ttyUSB0` in the terminal to grant permissions.

**Q: Why can't the ROS program run in VSCode?**

- A: Because the VSCode terminal cannot be loaded into the ROS environment, it needs to be run in the system terminal.

**Q: When rosrun is running, the terminal prompts `Unable to register with master node [http://localhost:11311]: master may not be running yet. Will keep trying`. What is the reason?**

- A: Before running the ROS program, you need to open the ROS node and enter `roscore` in the terminal.

**Q: When rosrun is running, the terminal error message shows `could not open port /dev/ttyUSB0: No such file or directory: '/dev/ttyUSB1'`. Why?**

- A: The serial port is wrong. It is necessary to confirm the actual serial port of the current robot arm. Can be viewed via `ls /dev/tty*`.

**Q: `catkin_make` failed to build the code in Ubuntu18.04, and the terminal prompted `Project 'cv_bridge' specifies '/usr/include/opencv' as an include dir, which is not found.` and other error messages**

- A: The OpenCV path in the configuration file does not match the actual path of the system. You need to

 use sudo to modify the configuration file (the path is `/opt/ros/melodic/share/cv_bridge/cmake/cv_bridgeConfig.cmake`). The actual OpenCV path of the system is located under the path `/usr/include/`.

**Q: Just clone the mycobot_ros package, and then run the rosrun program directly. An error such as `package 'mycobot_280' not found` or an error such as the file cannot be found appears?**

- A: The newly cloned mycobot_ros needs to build the code for the ROS environment compilation. Terminal input

```bash
cd ~/catkin_ws/
catkin_make
source devel/setup.bash
```

**Q: After compilation is completed, why does the following error appear when running the launch command in a new terminal?**

 <img src =../image/17.4.3-1.png
 align = "center">

- A1: The system does not add ROS environment variables, so every time you open a new terminal, you must source:

```bash
cd ~/catkin_ws/
source devel/setup.bash
```

- A2: The system adds ROS environment variables, and there is no need to execute source every time you open a new terminal:

```bash
# Noetic for Ubuntu20.04 system
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

- A3: It may be that the file name in the command is inconsistent with the actual file name in the mycobot_ros package. Please check carefully whether the command is correct.