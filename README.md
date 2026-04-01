# 🤖 KOBUKI ROS2 HUMBLE

This repository provides a complete guide and implementation for using **Kobuki packages and teleoperation (teleop)** with **ROS 2 Humble**.

---

## 📁 Repository

🔗 https://github.com/FBOTWork/kobuki_ros2.git

---

## 🚀 Installation Guide

### 📦 Prerequisites

Make sure you have installed:

- Ubuntu 22.04  
- ROS 2 Humble  
- Git  
- Zsh (optional but recommended)

---

## 📥 Clone the Repository

⚠️ This repository uses **Git submodules**, so clone it properly:

```bash
cd ~/ros2_ws/src
git clone --recurse-submodules https://github.com/FBOTWork/kobuki_ros2.git
```
## 🔧 Install Dependencies
```
cd ~/ros2_ws
rosdep update
rosdep install --from-paths src --ignore-src -r -y
```
## 🧹 Clean Build (Fix Errors)

If you encounter build errors (CMake issues, missing packages, etc.), clean the workspace:
```
cd ~/ros2_ws
rm -rf build/ install/ log/
```
## 🛠️ Build the Workspace
```
colcon build
```
## ⚙️ Source the Workspace
For current terminal:
```
source install/setup.bash
```
Automatically source every terminal:
```
echo "source ~/ros2_ws/install/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
## ▶️ Running Kobuki

Start the Kobuki base node:
```
ros2 launch kobuki_node kobuki_node-launch.py
```
## 🎮 Teleoperation

Control the robot using the keyboard:
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=commands/velocity
```
## 🔍 Debug Commands

List active topics:
```
ros2 topic list
```
Monitor velocity commands:
```
ros2 topic echo /commands/velocity
```
