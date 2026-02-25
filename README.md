# ROS & Gazebo Lab Reports

**Robotics & Mechatronics Engineering Master's | Polytech Nice-Sophia | Université Côte d’Azur**

This repository serves as a technical archive of laboratory reports for the **ROS & Gazebo** course. It documents the systematic development of robotic control systems, ranging from basic message passing in ROS 2 to the autonomous operation of multi-jointed robotic manipulators in simulated environments.

---

### 📂 Lab Documentation

The following reports detail the technical implementation, challenges, and results for each stage of the course:

* **[Lab 1 & 2: Introduction to ROS 2]**
* **Scope**: Development of custom C++ packages (`rclcpp`) to interface with `turtlesim`.
* **Key Features**: Implementation of a `MinimalPublisher` node to remap joystick (`/joy`) and keyboard velocity commands, utilizing a custom `params.yaml` for dynamic gain adjustments.


* **[Lab 3: Interbotix PX100 Control]**
* **Scope**: Low-level joint control and high-level MoveIt! integration for the PX100 arm.
* **Key Features**: Real-time joint state analysis via `/px100/joint_states` and the development of an orchestrated C++ node to cycle between predefined pick-and-place positions.


* **[Lab 4: Autonomous Arm Simulation]**
* **Scope**: Full physics simulation in Gazebo Fortress.
* **Key Features**: Custom URDF configuration for friction/contact physics and the creation of a non-blocking Python state machine for autonomous object manipulation.



---

### 🏗 Technical Focus: Kinematics & Control

A central theme throughout these labs is the management of complex **Forward and Inverse Kinematics** mechanisms required for precise manipulation:

* **Joint State Integration**: Implementation involved mapping high-level Cartesian goals to low-level angular positions (waist, shoulder, elbow, and wrist).
* **Trajectory Planning**: Leveraged MoveIt! to calculate collision-free paths, ensuring the 4-DOF manipulator reached goal states (like "upright" or "sleep") without violating joint limits.
* **Dynamic Response**: Addressed the physical complexities of simulated environments, such as overcoming joint friction and damping by identifying minimum velocity thresholds (e.g., 0.5 for gripper movement) to ensure reliable execution of commanded positions.

---

### 🛠 System Specifications

The implementations described in these reports were developed and tested using the following environment:

* **Operating System**: Ubuntu 22.04 LTS
* **Middleware**: ROS 2 Humble
* **Simulation**: Gazebo Fortress (Ignition)
* **Hardware Packages**: `interbotix_xsarm_ros_control`, `ros-humble-ros2-control`
