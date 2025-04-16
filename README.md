# simple_boxbot_v1

A minimal URDF-based box-shaped robot for ROS 2 + Gazebo simulation.  
ROS 2 や Gazebo シミュレーション用の、直方体ベースの最小URDFロボットです。

---

## 📦 Features / 特徴

- ✅ Simple box-based URDF model （シンプルな直方体URDFモデル）
- ✅ Compatible with Gazebo Classic and RViz2 （Gazebo・RViz2 両対応）
- ✅ Easily extendable for joint control or simulation tasks  
  （ジョイント制御や動作学習への拡張も容易）

---

## 🚀 Quick Start / クイックスタート

1. Build the package / パッケージのビルド

```bash
cd ~/ros2_ws
colcon build --packages-select simple_boxbot_v1
source install/setup.bash

2. Spawn in Gazebo / Gazeboに表示

ros2 launch gazebo_ros gazebo.launch.py &
ros2 run gazebo_ros spawn_entity.py \
  -entity simple_boxbot \
  -file ~/ros2_ws/src/simple_boxbot_v1/urdf/simple_boxbot.urdf

📁 Folder Structure / フォルダ構成

simple_boxbot_v1/
├── CMakeLists.txt
├── package.xml
├── launch/
│   └── display.launch.py
└── urdf/
    └── simple_boxbot.urdf

📖 License / ライセンス
This project is licensed under the MIT License.
このプロジェクトは MITライセンス で公開されています。


Designed and tested with ROS 2 Humble on Ubuntu 22.04 + Gazebo Classic.
動作確認環境：ROS 2 Humble + Ubuntu 22.04 + Gazebo Classic

