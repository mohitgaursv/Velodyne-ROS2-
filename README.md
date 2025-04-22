# Velodyne-ROS 2 
## Section 0: Prerequisites

### 1. Setting Up Your Computer to Communicate with the Velodyne Sensor

#### a) Power the LiDAR Sensor
Use the included power adapter to connect and power the Velodyne VLP-16 sensor.

#### b) Connect the LiDAR via Ethernet
Plug the sensor’s Ethernet cable into your computer’s Ethernet port.

#### c) Configure Your Computer's IP Address
Set your computer’s Ethernet IP address to be on the same subnet as the sensor.  
For example, if your Velodyne sensor has an IP `192.168.1.201`, set your PC's IP to something like `192.168.1.30`.


![image](https://github.com/user-attachments/assets/eebee064-4a0a-47e8-8949-f4ce3da195eb)

#### d) Checking the configurations

To check the connection open your web browser and access the following sensor’s network address: 192.168.XX.YY. 
The following page should appear:
![Screenshot from 2025-04-22 11-20-04](https://github.com/user-attachments/assets/1bec5600-27eb-46f1-adcf-899ff79c4e46)

#### e) Install the ROS Dependencies
```bash
sudo apt-get install ros-VERSION-velodyne
```
#### f) Clone or download the ROS-Velodyne Drivers


 1. Clone the Velodyne ROS 2 Repository

```bash
cd ~/ros2_vp/src/
git clone https://github.com/ros-drivers/velodyne-ros2.git
```



## Section 1: Workspace Setup
1. Source Your ROS 2 Workspace

```bash
source ~/ros2_vp/install/setup.bash
```
2. Navigate to Your Project Directory
a) Go to the velodyne-ros2 package directory
```bash
 cd ~/ros2_vp/velodyne-ros2

```

## Section 1: Launch the Velodyne-ROS2 drivers
1. Launch the Velodyne Driver Node: This node reads raw data packets from the VLP16 sensor.
   ```bash
   ros2 launch velodyne_driver velodyne_driver_node-VLP16-launch.py
   ```
## Section 2: Launch the Velodyne Transform Node
This node converts the raw packets into point cloud data using correction parameters.
```bash
ros2 launch velodyne_pointcloud velodyne_transform_node-VLP16-composed-launch.py
```
## Section 3: Visualize the data in Rviz2
```bash
rviz2
```
1. Set the fixed frame to velodyne
2. Go to Add option in bottom left screen and click on add.
3. Select by topic and add point cloud to view the data
![image](https://github.com/user-attachments/assets/73d2baed-dc3f-4b17-9cc8-a4e87ade39fd)
