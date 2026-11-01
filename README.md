# CARLA Camera–LiDAR Sensor Fusion
1.项目介绍

基于CARLA 0.9.15的摄像头、LiDAR及目标级融合感知对比实验，
用于研究车路协同碰撞预警场景下的目标检测、定位、测速和环境稳定性。
<img width="1379" height="1461" alt="e17a0b90d683cf036aa02b3295ebd7dc" src="https://github.com/user-attachments/assets/27cb3443-3e0e-42a1-98b3-0cdf400d69fa" />
<img width="1345" height="971" alt="65958f62e0b7e954f7e8132730ad8fdd" src="https://github.com/user-attachments/assets/379ec5b0-63c7-4ce3-bd6f-e7482ab5dd7e" />

2.主要功能

摄像头车辆检测与单目定位；
LiDAR ROI筛选和DBSCAN聚类；
LiDAR点云投影至摄像头图像；
摄像头—LiDAR目标级融合；
正常、强光、弱光和雨雾实验；
10～50 m距离实验；
部分遮挡实验；
5 m/s和10 m/s运动目标测速；
自动计算MAE、RMSE、正确率和处理时间。

3.环境要求

Windows 10/11
CARLA 0.9.15
Python 3.7.9 64-bit
NumPy 1.21.6
OpenCV 4.8.1
scikit-learn 1.0.2
Open3D 0.16.0

4. 安装步骤

包含：

创建虚拟环境；
安装本地CARLA wheel；
安装requirements；
下载YOLO模型；
启动CARLA服务器。

5. 主要结果

| 方法 | 正常20 m RMSE | 5 m/s速度MAE | 10 m/s速度MAE |
|---|---:|---:|---:|
| Camera | 0.4922 m | 2.1736 m/s | 2.4276 m/s |
| LiDAR | 0.1397 m | 0.0756 m/s | 0.0868 m/s |
| Fusion | 0.0456 m | 0.1053 m/s | 0.0952 m/s |

6. 局限性

仅使用CARLA仿真；
摄像头使用单目尺寸估距；
LiDAR算法为传统聚类；
未实现完整多目标跟踪；
融合回退门限固定；
CARLA标准LiDAR雨雾模拟有限；
结果主要用于受控实验下的方法对比。
