# LSR-visual-grasping

#### 介绍
生活支援机器人(第二版），使用kinova机械臂、Intel realsense D435i深度相机结合深度学习卷积神经网络视觉抓取算法完成日常生活中常见物体的抓取。


#### 环境配置
```
1.ros-noetic
2.opencv 4.2.0
3.opencv-conrib 4.2.0
环境2和3参考https://blog.csdn.net/u013454780/article/details/128357962
报错可能是需要sudo apt-get install ros-noetic-visp
```

#### 安装教程

1.  将aruco_ros-noetic-devel、easy_handeye-master、vision_visp-noetic-devel功能包下载到工作空间
2. 编译工作空间

1）
```
catkin_make
```
编译aruco_ros-noetic-devel和easy_handeye-master功能包

2）
```
catkin_make --pkg visp_hand2eye_calibration
```
单独编译vision_visp-noetic-devel的visp_hand2eye_calibration功能包（全部一起编译会不通过）

#### 使用说明

1.  
```
roslaunch easy_handeye eye_on_hand_calibration.launch
```
出现以下界面
![输入图片说明](images/2023-05-15%2010-24-21%20%E7%9A%84%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE.png)

2.  改变机械臂末端位姿获得一组位姿与相机坐标系到aruco二维码的转换关系，点击Take Sample记录结果。重复采样20组后，点击Compute，获得手眼标定结果。（自动存放在~/.ros/easy_handeye/目录下）



