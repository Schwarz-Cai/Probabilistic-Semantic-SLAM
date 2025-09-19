# Probabilistic Semantic SLAM: Enhancing Indoor Navigation in Dynamic Environments
Simultaneous Localization and Mapping (SLAM) is pivotal for autonomous navigation in unknown environments. However, conventional SLAM systems often struggle in dynamic scenarios due to their reliance on static scene assumptions.
To address this limitation, we present an enhanced semantic SLAM framework designed for dynamic indoor environments. Our approach builds upon ORB-SLAM3 and integrates real-time semantic segmentation using YOLOv8. A dynamic probability propagation mechanism is introduced to robustly identify static feature points within regions containing moving objects. Furthermore, geometric cues from depth images are incorporated to refine mask boundaries, reducing noise artifacts in point cloud maps. Through multi-level feature screening and mask optimization, our method produces high-precision global reconstructions. Extensive experiments on the TUM dataset demonstrate that our approach significantly reduces both Absolute Trajectory Error (ATE) and Relative Pose Error (RPE), surpassing classical SLAM and other dynamic SLAM baselines. These results highlight the effectiveness of our framework in improving robustness and accuracy of SLAM in complex dynamic indoor scenes.

This repository contains the official implementation of our paper.  
The codebase is managed and maintained by our research lab as part of our shared research efforts.
# Usage

catkin_make -DCATKIN_WHITELIST_PACKAGES="slam_track"

conda activate yolov8

roslaunch astra_camera astra.launch

rosrun slam yolov8_action_server

roslaunch slam_track room_RGB-D.launch

roslaunch robot_driver robot_run.launch

roslaunch robot_cl keybord.launch

evo_ape tum CameraTrajectory.txt CameraTrajectory.txt -a -p -s

# Note
The code is mainly based on ORB-SLAM3(https://github.com/UZ-SLAMLab/ORB_SLAM3) .
The test dataset can be download at TUM : https://cvg.cit.tum.de/data/datasets/rgbd-dataset/download; 
