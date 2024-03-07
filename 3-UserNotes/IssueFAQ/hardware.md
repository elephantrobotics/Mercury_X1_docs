# Hardware Problems

## 1 About Structure

**Q: How to solve the problem of the robot arm shaking?**

- A: To resolve the shaking issue:
  1. Enter myStudio and burn the latest version of AtomMAIN firmware to the ATOM of the robotic arm.
  2. Update the pymycobot version by running the following command in the terminal: `pip install pymycobot --upgrade --user`.
  3. Download the `pid_read_write.py` file from [GitHub](https://github.com/elephantrobotics/pymycobot/tree/main/demo) and save it to your computer or Raspberry Pi system.
  4. Modify each parameter configuration in the `pid_read_write.py` file according to the servo number. The parameter serial number corresponds to the serial number displayed in the picture one-to-one.
  5. Run the modified code.

   ![demo.jpg](../image/demo.jpg)

   ![280.png](../image/280.png)

  Note: Joint parameters for each robot arm are not uniform and need to be compared and modified according to the corresponding robot arm model.

**Q: What are the limits of myCobot’s joints?**

- A: The one-axis and five-axis joints have limited positions. One-axis is about 160° clockwise and about 160° counterclockwise. Five axes can rotate clockwise and counterclockwise about 160°.
  
  Note: When rotating the mechanical arm, it should be rotated at a small angle and gently. After reaching the limit, do not use force to continue rotating.

**Q: What are the six servos controlled by?**

- A: The servos are controlled by the Atom on the top.

**Q: What is the role of atoms in the robotic arm?**

- A: Atom mainly controls the kinematic algorithm of the robotic arm, including forward and inverse kinematics, solution selection, acceleration and deceleration, speed synchronization, multi-power interpolation, coordinate conversion, etc. Atom-related programs are not open source yet.

**Q: Why is there no display on the screen when the microprocessor-based robotic arm is connected to the HDMI interface? Do I need to download the serial port driver?**

- A: Check whether the wiring is correct and whether the power switch is on. Try changing the HDMI interface. The interface part must be inserted firmly. No need to download a serial port driver.
  
  Another situation is that you may power on the robotic arm first and then connect the HDMI cable. This will also result in no input signal to the monitor. You need to completely connect the HDMI cable when the robotic arm is not powered on, and then connect the adapter (or turn on the toggle switch after the adapter is connected).

**Q: What communication interfaces do different versions of robotic arms support?**

- A: The microprocessor-based robotic arm supports socket communication TCP, and the microcontroller-based robotic arm can convert USB to serial port communication.

**Q: The motor automatically cuts off power during use. Why?**

- A: The motor has overheating protection when used for a long time. This phenomenon is normal, and you can continue using it after a few minutes.

**Q: Does the robotic arm support Android development?**

- A: We currently do not have a direct Android development environment, and development needs to be done independently. We provide a serial port protocol, and the serial port can be developed twice.

## 2 About Parameters

**Q: What is the speed unit of the robotic arm?**

- A: The operating speed is 180 degrees/second.

**Q: What is the communication frequency of mycobot280-M5?**

- A: The communication frequency is 10-20Hz.

## 3 About the End Holder

**Q: Can the adaptive gripper not be fully closed?**

- A: There will be a certain gap between the jaws themselves, and they are not completely closed. You can adjust it by increasing the thickness of the spacer between them.

**Q: What is the communication function of mycobot280 adaptive gripper?**

- A: The mycobot280 adaptive gripper uses TTL communication.

**Q: How to fix the USB camera at the end of the robotic arm?**

- A: It needs to be fixed with a flange, which can be purchased independently.