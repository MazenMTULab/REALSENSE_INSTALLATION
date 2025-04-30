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
cd ~/real_camera_ws/src
git clone https://github.com/IntelRealSense/realsense-ros.git
cd ~/real_camera_ws
colcon build --symlink-install
```

```
ros2 run realsense2_camera realsense2_camera_node
```

```
ros2 topic list
```
```


    /camera/camera/color/camera_info
    /camera/camera/color/image_raw
    /camera/camera/color/metadata
    /camera/camera/depth/camera_info
    /camera/camera/depth/image_rect_raw
    /camera/camera/depth/metadata
    /camera/camera/extrinsics/depth_to_color
    /camera/camera/extrinsics/depth_to_depth
    /camera/camera/extrinsics/depth_to_infra1
    /camera/camera/extrinsics/depth_to_infra2
    /camera/camera/infra1/camera_info
    /camera/camera/infra1/image_rect_raw
    /camera/camera/infra1/metadata
    /camera/camera/infra2/camera_info
    /camera/camera/infra2/image_rect_raw
    /camera/camera/infra2/metadata
```
