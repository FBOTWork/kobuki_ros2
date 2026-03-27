# 🤖 KOBUKI ROS2 HUMBLE

This repository provides a guide and implementation for using **Kobuki packages and teleoperation (teleop)** with ROS 2 Humble.

## 📁 Repository

🔗 GitHub: https://github.com/FBOTWork/kobuki_ros2.git

---

## 🚀 Installation Guide

### 📦 Prerequisites

Make sure you have:

* Ubuntu 22.04
* ROS 2 Humble
* Git
* Zsh

---

## 📥 Clone the Repository

⚠️ This repository uses **Git submodules**. You must clone it properly:

```bash
cd ~/ros2_ws/src
git clone --recurse-submodules https://github.com/FBOTWork/kobuki_ros2.git
```
---

## 🔧 Install Dependencies

```bash id="3wczap"
cd ~/ros2_ws
rosdep update
rosdep install --from-paths src --ignore-src -r -y
```

---

## 🛠️ Build the Workspace

```bash id="h4v7jg"
colcon build
```

---

## ⚙️ Source the Workspace (bash)

```bash id="4czmci"
source install/setup.bash
```

To automatically source every time you open the terminal:

```bash id="l8hz9k"
echo "source ~/ros2_ws/install/setup.bash" >> ~/.bashrc
```

Then reload:

```bash id="yssbdl"
source ~/.bashrc
```

---

## ▶️ Running Kobuki

Start the Kobuki base node:

```bash id="8e98we"
ros2 launch kobuki_node kobuki_node-launch.py
```

---

## 🎮 Teleoperation

Control the robot using your keyboard (with correct topic remapping):

```bash id="wbd0wh"
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=commands/velocity
```

---

## 🔍 Debug Commands

Check active topics:

```bash id="3x6l0u"
ros2 topic list
```

See velocity commands being sent:

```bash id="82ybw1"
ros2 topic echo /commands/velocity
```

---

## 📌 Notes

* Ensure Kobuki is connected via USB
* Check the port (e.g., `/dev/ttyUSB0`)
* Kobuki uses `commands/velocity` instead of `cmd_vel`
* Always source your workspace (`setup.bash`) before running

---

## ✅ Done!

Now you can fully control your Kobuki robot using ROS 2 Humble using Bash 🚀