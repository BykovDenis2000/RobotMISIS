# Инструкция

### 1. Установить ROS 2 Humble по этой инструкции: https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html

### 2. Добавить сурс в bashrc для удобства: 

```bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
```
### 3. Установить дополнительные либы:

```bash
sudo apt install ros-humble-xacro ros-humble-ros2-control ros-humble-ros2-controllers
```

### 4. Создать воркспейс и перейти в него

```bash
mkdir -p ~/dev_ws/src
cd ~/ros2_ws/src
```
### 5. Склонировать репозиторий в папку src:

```bash
https://github.com/BykovDenis2000/RobotMISIS
```
### 6. Добавить stl файл “chassis_v3” из гугл диска в директорию misis_robot/description/meshes/

### 7. Перейти в директорию dev_ws и забилдить:

```bash
colcon build –symlink-install
```
### 8. Засурсить

```bash
source install/setup.bash
```

### 9. Запустить симуляцию:

```bash
ros2 launch misis_robot launch_sim.launch.py world:=./src/misis_robot/worlds/TD3_very_large.world
```

### 10. Запустить модель из директории dev_ws/src/model

```bash
python3 train.py
```
