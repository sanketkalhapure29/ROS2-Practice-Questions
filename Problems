# 🤖 ROS2 Practical Mini-Project Roadmap

> **From Understanding ROS2 Concepts → Writing ROS2 Programs → Building Real Robot Systems**

This repository contains a structured set of **60 practical ROS2 mini-projects** designed to build programming logic, ROS2 implementation skills, debugging ability, and real-world robotics system-design skills.

The purpose of this roadmap is not simply to memorize ROS2 syntax.

The main goal is:

> **Given a robotics problem, learn how to break it into nodes, decide how nodes should communicate, structure the code, implement it, debug it, and finally combine everything into a complete robotic system.**

---

# 🎯 Learning Objective

After completing these projects, you should be able to:

* Create ROS2 workspaces and packages
* Create Python and C++ ROS2 nodes
* Structure a ROS2 program from scratch
* Use timers, classes, functions, and callbacks
* Understand ROS2 node architecture
* Use ROS2 CLI tools for debugging
* Understand and implement Topics
* Create Publishers and Subscribers
* Understand and implement Services
* Create Service Servers and Clients
* Use `rqt` and `rqt_graph`
* Work with Turtlesim
* Create XML and Python launch files
* Use launch-file remapping
* Load parameters
* Design multi-node robotic systems
* Decide when to use Topics vs Services
* Debug ROS2 communication problems
* Build small real-world robotic applications

---

# 🧠 How to Use This Roadmap

Do **not** immediately look for the solution.

For every project, follow this process:

```text
1. Understand the problem
        ↓
2. Identify required information
        ↓
3. Identify required nodes
        ↓
4. Decide what each node should do
        ↓
5. Decide how nodes communicate
        ↓
6. Draw the ROS2 architecture
        ↓
7. Write pseudocode
        ↓
8. Implement the code
        ↓
9. Build using colcon
        ↓
10. Test using ROS2 CLI
        ↓
11. Debug using rqt / rqt_graph
        ↓
12. Improve the implementation
```

---

# 📁 Recommended Workspace Structure

Create one workspace for the complete roadmap:

```text
ros2_practice_ws/
│
├── src/
│   ├── section2_basics/
│   ├── section3_tools/
│   ├── section4_topics/
│   ├── section5_services/
│   ├── section6_launch/
│   └── integrated_projects/
│
├── build/
├── install/
└── log/
```

You may also organize packages according to the project.

---

# 🟢 SECTION 2 — Writing Your First ROS2 Programs

## Objective

Learn how to create ROS2 workspaces, packages, nodes, Python/C++ programs, classes, functions, timers, and basic robot logic.

---

# Project 01 — Robot Heartbeat

### Difficulty

⭐ Beginner

### Problem Statement

A robot controller should continuously indicate that the robot software is running correctly.

Create a ROS2 Python node named:

```text
robot_health
```

The node must periodically print a heartbeat message.

Example:

```text
Robot is alive
Heartbeat: 1
Heartbeat: 2
Heartbeat: 3
...
```

### Requirements

* Create a ROS2 workspace.
* Create a Python package.
* Create a ROS2 node.
* Use a timer.
* Maintain a heartbeat counter.
* Display the counter periodically.

### Robotics Application

Real robots often contain monitoring or diagnostic systems that periodically verify whether critical software components are still running.

### Expected Outcome

You should be able to create a complete ROS2 Python node starting from an empty package.

---

# Project 02 — Battery Monitor

### Difficulty

⭐ Beginner

### Problem Statement

A mobile robot must continuously monitor its battery level.

Create a node that simulates a battery starting at:

```text
100%
```

and gradually decreases the battery level.

The node must display different warnings depending on the battery level.

### Required Logic

```text
Battery > 20%
→ NORMAL

Battery <= 20%
→ LOW BATTERY WARNING

Battery <= 5%
→ CRITICAL BATTERY
```

### Example

```text
Battery: 72%
Status: NORMAL

Battery: 19%
Status: LOW BATTERY WARNING

Battery: 4%
Status: CRITICAL BATTERY
```

### Robotics Application

Battery monitoring is essential for UGVs, AGVs, drones, and autonomous mobile robots.

---

# Project 03 — Motor Temperature Monitor

### Difficulty

⭐⭐

### Problem Statement

A robot's motor temperature must be monitored to prevent overheating.

Create a node that simulates motor temperature.

### Required Logic

```text
< 60°C
→ NORMAL

60–80°C
→ WARNING

> 80°C
→ OVERHEAT
```

### Expected Output

```text
Motor Temperature: 55°C
Status: NORMAL

Motor Temperature: 72°C
Status: WARNING

Motor Temperature: 85°C
Status: OVERHEAT
```

### Robotics Application

Industrial robots and mobile robots can monitor actuator and motor temperatures to prevent hardware damage.

---

# Project 04 — Emergency Stop Monitor

### Difficulty

⭐⭐

### Problem Statement

Create a ROS2 node that represents an emergency-stop system.

Use a variable to simulate the emergency switch.

```text
False → Safe
True  → Emergency Stop
```

### Expected Behavior

When the emergency stop is inactive:

```text
Robot Status: SAFE
Motors: ENABLED
```

When activated:

```text
EMERGENCY STOP!
Motors: DISABLED
```

### Challenge

Use a ROS2 timer rather than a continuous `while` loop.

---

# Project 05 — UGV Status Monitor

### Difficulty

⭐⭐

### Problem Statement

Create a node that maintains the current status of a UGV.

The robot should contain:

```text
Speed
Direction
Battery
Motor Temperature
```

Display the complete status periodically.

### Example

```text
========== UGV STATUS ==========

Speed       : 1.5 m/s
Direction   : FORWARD
Battery     : 82%
Temperature : 48°C

================================
```

### Challenge

Create separate functions for updating:

```text
Battery
Temperature
Speed
Status Display
```

Do not put all logic into one function.

---

# Project 06 — Obstacle Distance Monitor

### Difficulty

⭐⭐⭐

### Problem Statement

Create a node that simulates an ultrasonic or LiDAR distance sensor.

The distance should change over time.

### Required Logic

```text
Distance > 2 m
→ CLEAR

1–2 m
→ CAUTION

0.5–1 m
→ WARNING

< 0.5 m
→ STOP
```

### Example

```text
Obstacle Distance: 0.35 m
Status: EMERGENCY STOP
```

### Robotics Application

This represents the basic logic used in collision avoidance systems.

---

# Project 07 — UGV Mission State Machine

### Difficulty

⭐⭐⭐

### Problem Statement

Create a node that manages the current state of a UGV mission.

Possible states:

```text
IDLE
MOVING
OBSTACLE_DETECTED
STOPPED
LOW_BATTERY
MISSION_COMPLETE
```

The program should change states according to different conditions.

### Example

```text
IDLE
 ↓
MOVING
 ↓
OBSTACLE_DETECTED
 ↓
STOPPED
```

### Robotics Application

State machines are commonly used for mission management and robot behavior.

---

# Project 08 — Differential Drive Calculator

### Difficulty

⭐⭐⭐⭐

### Problem Statement

Create a ROS2 node that calculates individual wheel velocities for a differential-drive robot.

Inputs:

```text
Linear velocity
Angular velocity
Wheel separation
```

Calculate:

```text
Left wheel velocity
Right wheel velocity
```

Use:

```text
v_left  = v - (ωL / 2)

v_right = v + (ωL / 2)
```

### Robotics Application

This directly represents the conversion from robot velocity commands to differential-drive wheel commands.

---

# Project 09 — Robot Diagnostic System

### Difficulty

⭐⭐⭐⭐

### Problem Statement

Create a diagnostic node for a UGV.

The robot contains:

```text
Battery
Motor
GPS
IMU
Camera
LiDAR
Motor Controller
```

Each subsystem must report:

```text
OK
WARNING
ERROR
```

### Example

```text
Battery       : OK
Motor         : OK
GPS           : OK
IMU           : OK
Camera        : ERROR
LiDAR         : OK

Robot Status: DEGRADED
```

### Challenge

Create separate functions for checking different systems.

---

# Project 10 — Robot Startup Sequence

### Difficulty

⭐⭐⭐⭐⭐

### Problem Statement

Create a startup/initialization node for a robot.

When the robot starts, it should sequentially check:

```text
Battery
Motor Controller
IMU
LiDAR
GPS
```

### Expected Sequence

```text
Initializing robot...

Checking battery...
Battery OK

Checking motor controller...
Motor Controller OK

Checking IMU...
IMU OK

Checking LiDAR...
LiDAR OK

Checking GPS...
GPS OK

All systems ready.

Robot READY.
```

If a component fails:

```text
LiDAR ERROR

Robot cannot start.

Startup aborted.
```

### Objective

Practice:

* Classes
* Functions
* Conditions
* Timers
* Program structure
* Error handling

---

# 🔵 SECTION 3 — Introduction to ROS2 Tools

## Objective

Learn how to inspect, debug, build, and understand ROS2 systems using command-line and graphical tools.

---

# Project 11 — Find the Robot

### Problem Statement

Run a ROS2 node without looking at its source code.

Use ROS2 CLI to determine:

* Node name
* Publishers
* Subscribers
* Services
* Other communication information

Use:

```bash
ros2 node list
ros2 node info <node_name>
```

### Objective

Learn how to inspect an unknown ROS2 node.

---

# Project 12 — Rename the Robot Node

### Problem Statement

Create a node named:

```text
robot_controller
```

Run the same executable while changing its runtime name to:

```text
ugv_controller
```

### Objective

Understand the difference between:

* Name defined in source code
* Name assigned at runtime

---

# Project 13 — Build Failure Challenge

### Problem Statement

Create multiple ROS2 packages.

Intentionally introduce an error in one package.

Build the workspace using:

```bash
colcon build
```

Determine:

* Which package failed?
* What caused the failure?
* Which packages succeeded?
* How can the problem be fixed?

### Objective

Learn to read and understand `colcon` errors.

---

# Project 14 — Multi-Package Robot Workspace

### Problem Statement

Create a workspace containing:

```text
sensor_pkg
controller_pkg
monitoring_pkg
```

Each package must contain at least one ROS2 node.

### Objective

Understand how multiple ROS2 packages form a larger robot software workspace.

---

# Project 15 — Visualize a Robot System

### Problem Statement

Create three nodes:

```text
Sensor
Controller
Monitor
```

Connect them using ROS2 communication.

Use:

```bash
rqt_graph
```

to visualize the complete system.

### Objective

Understand ROS2 computational graphs.

---

# Project 16 — Dead Node Debugging

### Problem Statement

Create a system where one node depends on another node.

Stop the first node while the system is running.

Use ROS2 CLI and `rqt_graph` to determine:

* Which node disappeared?
* Which communication stopped?
* What changed in the graph?

### Objective

Develop ROS2 debugging skills.

---

# Project 17 — Turtlesim Emergency Stop

### Problem Statement

Use Turtlesim to create a simple safety scenario.

The turtle should normally move.

When an emergency condition occurs, the turtle should stop.

### Objective

Understand how existing ROS2 nodes communicate and how Turtlesim can be used to learn ROS2 behavior.

---

# Project 18 — Reverse Engineer Turtlesim

### Problem Statement

Run Turtlesim and teleoperate the turtle.

Without reading source code, discover:

* Which nodes are running?
* Which topic controls the turtle?
* Which node publishes velocity?
* Which node receives velocity?
* What messages are being exchanged?

Use:

```bash
ros2 node list
ros2 topic list
ros2 topic info
ros2 topic echo
rqt_graph
```

### Objective

Learn to investigate an existing ROS2 system.

---

# Project 19 — Unknown Robot Investigation

### Problem Statement

Imagine you have received an unfamiliar ROS2 robot system.

You are not allowed to inspect the source code.

Determine:

```text
Running Nodes
Topics
Services
Publishers
Subscribers
Communication Graph
```

### Objective

Practice the same debugging process used when working with an unfamiliar robot codebase.

---

# Project 20 — ROS2 Debugging Challenge

### Problem Statement

Create a system containing:

```text
3 nodes
4 topics
2 services
```

Intentionally break one communication path.

Your task is to identify the problem using only:

```text
ros2 node
ros2 topic
ros2 service
rqt
rqt_graph
```

### Objective

Develop independent debugging ability.

---

# 🟡 SECTION 4 — ROS2 Topics

## Objective

Learn how ROS2 nodes continuously exchange information using Topics.

---

# Project 21 — Battery Publisher and Monitor

### Problem Statement

Create two nodes:

```text
battery_sensor
battery_monitor
```

The sensor publishes battery percentage.

The monitor subscribes and displays the battery level.

Architecture:

```text
battery_sensor
      |
      | /battery
      ↓
battery_monitor
```

---

# Project 22 — Motor Temperature System

### Problem Statement

Create:

```text
temperature_sensor
motor_controller
```

The temperature node publishes motor temperature.

The controller subscribes and determines whether the motor should operate normally.

### Logic

```text
Temperature < 70°C
→ Motor allowed

Temperature >= 70°C
→ Motor limited
```

---

# Project 23 — Obstacle Detection System

### Problem Statement

Create:

```text
distance_sensor
obstacle_detector
```

The distance sensor publishes distance.

The obstacle detector determines:

```text
CLEAR
WARNING
STOP
```

---

# Project 24 — Autonomous Speed Controller

### Problem Statement

Create:

```text
distance_sensor
obstacle_detector
speed_controller
```

### Required Behavior

```text
Distance > 2 m
→ Speed = 1.5 m/s

Distance 1–2 m
→ Speed = 0.7 m/s

Distance < 1 m
→ Speed = 0 m/s
```

### Objective

Build a basic sensor-to-decision-to-control pipeline.

---

# Project 25 — GPS Simulation

### Problem Statement

Create a GPS node that publishes simulated:

```text
Latitude
Longitude
```

Create a second node that subscribes to the GPS data and displays the robot's position.

---

# Project 26 — IMU Simulation

### Problem Statement

Create an IMU node that publishes:

```text
Roll
Pitch
Yaw
```

Create an orientation monitor that subscribes to the data.

### Objective

Understand continuous sensor data communication.

---

# Project 27 — Basic Sensor Fusion

### Problem Statement

Create:

```text
GPS Node
IMU Node
Localization Node
```

The localization node subscribes to both GPS and IMU information.

Architecture:

```text
GPS ─────┐
         ↓
     Localization
         ↑
IMU ─────┘
```

### Objective

Understand the architecture behind multi-sensor localization.

> Do not implement a real EKF yet. Focus on ROS2 communication and data flow.

---

# Project 28 — Differential Drive Motor Controller

### Problem Statement

Create:

```text
teleoperation_node
motor_controller
```

The teleoperation node publishes:

```text
linear_velocity
angular_velocity
```

The motor controller subscribes and calculates:

```text
left_wheel_velocity
right_wheel_velocity
```

### Robotics Application

This represents the communication architecture between a velocity command source and a mobile robot motor controller.

---

# Project 29 — Robot Safety Controller

### Problem Statement

Create a safety controller that subscribes to:

```text
obstacle_status
battery_status
```

### Logic

```text
Obstacle detected
→ STOP

Low battery
→ LIMIT SPEED

Critical battery
→ STOP

Everything normal
→ NORMAL OPERATION
```

### Objective

Combine multiple sensor topics into a single robot decision.

---

# Project 30 — Mini Autonomous UGV

### Problem Statement

Build a multi-node simulated UGV system.

Required nodes:

```text
GPS
IMU
Obstacle Sensor
Battery Sensor
Localization
Decision Controller
Speed Controller
Motor Controller
```

Architecture:

```text
GPS ──────────────┐
IMU ──────────────┤
Obstacle Sensor ──┤
Battery Sensor ───┤
                  ↓
             Decision Node
                  ↓
            Speed Controller
                  ↓
            Motor Controller
```

### Objective

Build your first complete topic-based ROS2 robot system.

---

# 🟠 SECTION 5 — ROS2 Services

## Objective

Learn request-response communication between ROS2 nodes.

---

# Project 31 — Reset Robot Service

### Problem Statement

Create a service:

```text
/reset_robot
```

The client requests a robot reset.

The server responds:

```text
Robot reset successfully
```

### Objective

Understand the basic Service Server and Client architecture.

---

# Project 32 — Start Mission Service

### Problem Statement

Create:

```text
/start_mission
```

The client sends a mission ID.

Example:

```text
Mission ID: 5
```

The server responds:

```text
Mission 5 started
```

---

# Project 33 — Battery Calibration Service

### Problem Statement

Create:

```text
/calibrate_battery
```

Calling the service should reset the simulated battery measurement to its initial calibrated state.

---

# Project 34 — Set Maximum Speed Service

### Problem Statement

Create:

```text
/set_max_speed
```

The client sends:

```text
max_speed = 1.5
```

The server updates the robot's maximum allowed speed.

---

# Project 35 — Get Robot Status Service

### Problem Statement

Create:

```text
/get_robot_status
```

The client requests the current robot status.

The server should return information such as:

```text
Battery
Temperature
Speed
Mission Status
```

### Objective

Understand when a service is more appropriate than a continuously published topic.

---

# Project 36 — Move Robot to Position

### Problem Statement

Create:

```text
/move_to_position
```

The client sends:

```text
x
y
```

The server validates the requested position and returns whether the command was accepted.

### Important

Do not implement real navigation.

Focus on:

```text
Request
→ Validation
→ Response
```

---

# Project 37 — Reset Sensors

### Problem Statement

Create:

```text
/reset_sensors
```

The service should simulate resetting:

```text
GPS
IMU
LiDAR
Camera
```

The server should return the reset status.

---

# Project 38 — Motor Enable/Disable Service

### Problem Statement

Create:

```text
/enable_motors
```

The client sends:

```text
true
```

or:

```text
false
```

The server updates the motor state.

### Example

```text
Request:
true

Response:
Motors enabled
```

---

# Project 39 — Mission Management Services

### Problem Statement

Create a mission-management node with:

```text
/start_mission
/stop_mission
/pause_mission
/resume_mission
```

The node should maintain the mission state.

### Possible States

```text
IDLE
RUNNING
PAUSED
STOPPED
COMPLETED
```

---

# Project 40 — UGV Command Center

### Problem Statement

Build a small command-center system.

### Services

```text
/start_mission
/stop_mission
/pause_mission
/resume_mission
/get_status
```

### Topics

```text
/battery
/temperature
/obstacle
/robot_state
```

### Objective

Learn to decide:

```text
Should this information be a Topic?

OR

Should this operation be a Service?
```

This is an important ROS2 system-design skill.

---

# 🔴 SECTION 6 — ROS2 Launch Files

## Objective

Learn how to start and configure complete ROS2 systems using launch files.

---

# Project 41 — Launch a Single Node

### Problem Statement

Create a launch file that starts your battery-monitor node.

Instead of:

```bash
ros2 run <package> <node>
```

you should be able to start it using:

```bash
ros2 launch <package> <launch_file>
```

---

# Project 42 — Launch Sensor System

### Problem Statement

Create one launch file that starts:

```text
Battery
Temperature
GPS
IMU
```

### Objective

Understand how multiple ROS2 nodes can be started together.

---

# Project 43 — Complete UGV Launch

### Problem Statement

Create a launch file that starts:

```text
GPS
IMU
Obstacle Sensor
Battery
Localization
Controller
Motor Controller
```

### Objective

Create a complete robot bringup launch file.

---

# Project 44 — XML Launch File

### Problem Statement

Recreate your UGV launch system using an XML launch file.

### Objective

Understand how ROS2 launch files can be written using XML.

---

# Project 45 — Topic Remapping

### Problem Statement

Suppose a node publishes:

```text
/cmd_vel
```

You want the robot system to use:

```text
/ugv/cmd_vel
```

Use a launch file to remap the topic.

Verify the result using:

```bash
ros2 topic list
```

---

# Project 46 — Multi-Robot Launch

### Problem Statement

Launch three simulated robots:

```text
robot1
robot2
robot3
```

Each robot must have independent communication.

Example:

```text
/robot1/cmd_vel
/robot2/cmd_vel
/robot3/cmd_vel
```

### Objective

Understand namespaces and remapping for multi-robot systems.

---

# Project 47 — Launch Parameters

### Problem Statement

Create a robot controller with configurable parameters:

```text
max_speed
minimum_battery
safe_distance
```

Load these values from a launch file.

Example:

```text
max_speed = 1.5
safe_distance = 0.8
minimum_battery = 20
```

---

# Project 48 — Different Robot Configurations

### Problem Statement

Create two launch configurations:

```text
small_ugv.launch.py
large_ugv.launch.py
```

Both should use the same nodes but different parameters.

Example:

```text
Small UGV
max_speed = 1.0

Large UGV
max_speed = 2.0
```

### Objective

Understand how parameters allow the same software to support different robots.

---

# Project 49 — Simulation Launch

### Problem Statement

Create one launch file that starts the complete simulation environment.

It should start:

```text
Robot
Sensors
Controller
Visualization
```

The complete system should start using one command.

---

# Project 50 — Production-Style UGV Bringup

### Problem Statement

Create a package structured approximately as:

```text
ugv_bringup/
│
├── launch/
│   ├── ugv.launch.py
│   └── simulation.launch.py
│
├── config/
│   └── ugv.yaml
│
└── package.xml
```

The launch system should:

* Load parameters
* Start required nodes
* Apply remappings
* Start the robot system

### Objective

Move from small exercises toward the structure of a real ROS2 robot software package.

---

# 🔥 SECTION 7 — INTEGRATED ROBOTICS PROJECTS

The following projects combine multiple ROS2 concepts.

These projects are intentionally harder.

---

# Project 51 — Smart Battery Management System

### Problem Statement

Build a complete battery-management system.

### Nodes

```text
Battery Sensor
Battery Monitor
Robot Controller
```

### Topic

```text
/battery
```

### Service

```text
/reset_battery
```

### Launch

Start the complete system using one launch file.

### Objective

Combine:

```text
Node
Topic
Subscriber
Service
Launch
```

---

# Project 52 — Obstacle Avoidance Robot

### Problem Statement

Build a robot that automatically changes its speed according to obstacle distance.

### Architecture

```text
Distance Sensor
       ↓
Obstacle Detector
       ↓
Speed Controller
       ↓
Motor Controller
```

### Service

```text
/set_max_speed
```

### Objective

Build a basic autonomous control pipeline.

---

# Project 53 — Autonomous UGV

### Problem Statement

Build a simulated autonomous UGV containing:

```text
GPS
IMU
Obstacle Sensor
Battery
Localization
Decision Controller
Motor Controller
```

### Communication

Use Topics for continuous sensor information.

Use Services for robot commands.

Use Launch files to start the system.

---

# Project 54 — Robot Health System

### Problem Statement

Build a central health-monitoring system.

Monitor:

```text
Battery
Motor Temperature
GPS
IMU
LiDAR
Camera
```

Each subsystem should report its health.

The central system should determine:

```text
HEALTHY
WARNING
DEGRADED
CRITICAL
```

### Service

```text
/reset_sensors
```

---

# Project 55 — Warehouse AGV

### Problem Statement

Create a simulated warehouse AGV.

The robot should contain:

```text
Mission Manager
Navigation Node
Obstacle Detection
Localization
Motor Controller
Battery Monitor
```

### Services

```text
/start_mission
/stop_mission
/get_status
```

### Topics

```text
/obstacle
/pose
/cmd_vel
/battery
```

### Objective

Build a simplified warehouse mobile robot architecture.

---

# Project 56 — Search and Rescue UGV

### Problem Statement

Create a simulated search-and-rescue robot.

Mission flow:

```text
START
 ↓
SEARCH
 ↓
TARGET FOUND
 ↓
STOP
 ↓
REPORT
```

### Sensors

Simulate:

```text
GPS
IMU
Obstacle Sensor
Camera Detection
Battery
```

### Objective

Practice state machines, sensor information, mission management, and robot behavior.

---

# Project 57 — Multi-Robot Warehouse

### Problem Statement

Create three robots operating inside the same ROS2 system.

```text
Robot 1
Robot 2
Robot 3
```

Each robot must have:

```text
Battery
Sensor
Controller
Motor Controller
```

Communication must remain independent.

Example:

```text
/robot1/cmd_vel
/robot2/cmd_vel
/robot3/cmd_vel
```

### Objective

Learn:

* Namespaces
* Remapping
* Multi-robot architecture
* Launch files

---

# Project 58 — Robotic Arm Controller

### Problem Statement

Create a simplified robotic-arm control system.

Architecture:

```text
Command Node
      ↓
Joint Controller
      ↓
Joint 1
Joint 2
Joint 3
```

### Topic

```text
/joint_states
```

### Services

```text
/move_to_pose
/enable_arm
/disable_arm
```

### Objective

Apply ROS2 concepts to robotic manipulation instead of mobile robots.

---

# Project 59 — Industrial Robot Safety System

### Problem Statement

Create a safety controller for an industrial robotic system.

### Inputs

```text
Emergency Stop
Obstacle
Motor Temperature
Motor Status
```

### Required Logic

```text
Emergency Stop
→ STOP

Obstacle
→ STOP

Overtemperature
→ STOP

Everything OK
→ RUN
```

### Objective

Build a safety-oriented ROS2 control architecture.

---

# 🏆 Project 60 — Mini Autonomous Robot Stack

## Difficulty

⭐⭐⭐⭐⭐

This is the final foundation project.

Build a complete simulated autonomous robot software architecture.

### Sensors

```text
GPS
IMU
LiDAR
Camera
Battery
```

### Processing

```text
Localization
Decision / Mission Manager
Controller
```

### Actuation

```text
Motor Controller
```

### Architecture

```text
                  GPS
                   │
                  IMU
                   │
                 LiDAR
                   │
                Camera
                   │
                Battery
                   │
                   ↓
          ┌─────────────────┐
          │  Localization   │
          └────────┬────────┘
                   ↓
          ┌─────────────────┐
          │ Decision /      │
          │ Mission Manager │
          └────────┬────────┘
                   ↓
          ┌─────────────────┐
          │   Controller    │
          └────────┬────────┘
                   ↓
          ┌─────────────────┐
          │ Motor Controller│
          └─────────────────┘
```

---

## Required Topics

Implement topics for continuous information such as:

```text
/battery
/imu
/gps
/lidar
/camera
/robot_state
/cmd_vel
```

---

## Required Services

Implement services for operations such as:

```text
/start_mission
/stop_mission
/reset_robot
/get_robot_status
/enable_motors
```

---

## Required Parameters

Use parameters such as:

```text
max_speed
safe_distance
minimum_battery
motor_temperature_limit
```

---

## Required Launch System

The entire system should be started using:

```bash
ros2 launch <package> <launch_file>
```

---

## Required Debugging

You should be able to investigate the system using:

```bash
ros2 node list
ros2 node info <node>
ros2 topic list
ros2 topic info <topic>
ros2 topic echo <topic>
ros2 service list
ros2 service type <service>
rqt_graph
```

---

# 🧠 Project Completion Checklist

For every project, check the following:

```text
[ ] I understood the problem.

[ ] I identified the required nodes.

[ ] I identified what each node should do.

[ ] I decided whether communication requires
    a Topic or Service.

[ ] I drew the architecture.

[ ] I wrote pseudocode before coding.

[ ] I created the package correctly.

[ ] I wrote the node without copying the solution.

[ ] I successfully built using colcon.

[ ] I ran the node.

[ ] I tested the expected behavior.

[ ] I used ROS2 CLI for debugging.

[ ] I used rqt/rqt_graph where appropriate.

[ ] I fixed at least one problem myself.

[ ] I can explain my code without looking at it.
```

---

# 🛠️ When You Get Stuck

Do not immediately copy a complete solution.

Use the following progression.

## Level 1 — Think

Ask yourself:

```text
What information do I have?

What information do I need?

Who should produce it?

Who should consume it?

Should it be a Topic or Service?
```

---

## Level 2 — Draw

Example:

```text
Sensor
   │
   │ /distance
   ↓
Obstacle Detector
   │
   │ /obstacle_status
   ↓
Motor Controller
```

---

## Level 3 — Write Pseudocode

Example:

```text
Receive distance

If distance < safe distance:
    command STOP

Otherwise:
    command MOVE
```

---

## Level 4 — Write the Program Structure

Before writing detailed logic:

```python
import rclpy
from rclpy.node import Node


class MyNode(Node):

    def __init__(self):
        super().__init__("my_node")

        # Publishers
        # Subscribers
        # Timers
        # Variables


    # Callback functions


def main(args=None):

    # Initialize ROS2
    # Create node
    # Spin
    # Destroy node
    # Shutdown ROS2


if __name__ == "__main__":
    main()
```

Then fill it yourself.

---

# 🆘 How to Ask for Help

When you cannot solve a project, send:

```text
Project Number:
Project Name:

What I understood:

My architecture:

My pseudocode:

My current code:

The exact problem/error:

What I already tried:
```

For example:

```text
Project: 23
Obstacle Detection System

I understand that the distance sensor should publish
distance and the obstacle detector should subscribe.

My architecture:

distance_sensor
       ↓
obstacle_detector

My problem:

I don't know how to structure the subscriber callback.

My current code:
<code>
```

The goal is to **solve the problem with guidance**, not simply copy code.

---

# 🚀 Recommended Learning Order

Follow the projects sequentially:

```text
Projects 01–10
        ↓
ROS2 Programming Foundation
        ↓
Projects 11–20
        ↓
ROS2 Tools & Debugging
        ↓
Projects 21–30
        ↓
ROS2 Topics
        ↓
Projects 31–40
        ↓
ROS2 Services
        ↓
Projects 41–50
        ↓
Launch Files
        ↓
Projects 51–60
        ↓
Integrated Robot Systems
```

---

# 🎯 Final Goal

The final goal is not:

> "I know ROS2 syntax."

The final goal is:

> **"Give me a robotics problem and I can design the ROS2 architecture, decide the communication mechanism, structure the packages and nodes, implement the code, build it, run it, inspect it, and debug it."**

That is the skill this roadmap is designed to develop.

---

## 🤖 Target Architecture

Eventually, your thinking should naturally progress from:

```text
"I need to write a subscriber."
```

to:

```text
"I need an obstacle-detection node.

The sensor continuously produces distance data,
so I need a Topic.

The controller needs the obstacle state,
so another Topic is required.

The emergency reset is an operation,
so that should be a Service.

These nodes belong to the same robot system,
so I'll create a Launch file.

The safety distance should be configurable,
so I'll use a Parameter.

Then I'll inspect the complete graph
using rqt_graph."
```

That transition—from **knowing ROS2 concepts** to **designing ROS2 systems**—is the main objective of these 60 projects.
