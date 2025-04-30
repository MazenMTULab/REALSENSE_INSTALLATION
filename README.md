# REALSENSE_INSTALLATION

## INSTALLATION INVOLVES 2 SETUP

## Step 1: INSTALLING INTELRESENSE SDK2.0
Run the following on the terminal
```
sudo mkdir -p /etc/apt/keyrings
curl -sSf https://librealsense.intel.com/Debian/librealsense.pgp | sudo tee /etc/apt/keyrings/librealsense.pgp > /dev/null
```
```
echo "deb [signed-by=/etc/apt/keyrings/librealsense.pgp] https://librealsense.intel.com/Debian/apt-repo `lsb_release -cs` main" | \
sudo tee /etc/apt/sources.list.d/librealsense.list
sudo apt-get update
```
```
sudo apt-get install librealsense2-dkms
```
```
sudo apt-get install librealsense2-utils
```
connect camera and run the following
```
realsense-viewer
```

## Step 2: INSTALLING INTELREALSENSE WRAPPER
```
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src/
```
```
git clone https://github.com/IntelRealSense/realsense-ros.git -b ros2-master
cd ~/ros2_ws
```
```
sudo apt-get install python3-rosdep -y
sudo rosdep init # "sudo rosdep init --include-eol-distros" for Foxy and earlier
rosdep update # "sudo rosdep update --include-eol-distros" for Foxy and earlier
rosdep install -i --from-path src --rosdistro $ROS_DISTRO --skip-keys=librealsense2 -y
```
```
colcon build
```
```
ROS_DISTRO=humble
source /opt/ros/$ROS_DISTRO/setup.bash
cd ~/ros2_ws
. install/local_setup.bash
```
