# 具身智能相关项目索引

生成日期：2026-09-30

从 `/mnt/ssdmax` 筛选与**具身智能（Embodied AI）**相关的项目，按主题分类，并附上 GitHub 链接与简介。

> 仅整理项目信息与介绍，不推送环境、模型权重或第三方完整源码。
>
> 完整磁盘索引：[`PROJECTS.md`](./PROJECTS.md) · README 同步清单：[`README_SYNC.md`](./README_SYNC.md)

共收录 **67** 个相关项目。

## 目录

- VLA / 端到端策略（13）
- 世界模型（8）
- 操作 / 抓取 / 位姿（10）
- 运动规划 / 控制 / 教材（7）
- 感知 / SLAM / 三维重建（12）
- 移动机器人 / 真机工程（17）

## VLA / 端到端策略

### `lerobot`

- GitHub：[huggingface/lerobot](https://github.com/huggingface/lerobot)
- 本地路径：`/mnt/ssdmax/lerobot`
- README 副本：[`projects/lerobot/README.md`](./projects/lerobot/README.md)
- 简介：Hugging Face 机器人库：数据、模型与真实机器人训练/评测一体化工具链。

### `openvla`

- GitHub：[openvla/openvla](https://github.com/openvla/openvla)
- 本地路径：`/mnt/ssdmax/openvla`
- README 副本：[`projects/openvla/README.md`](./projects/openvla/README.md)
- 简介：开源视觉-语言-动作（VLA）模型，支持预训练、LoRA/全量微调与评测。

### `openvla_train`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/openvla_train`
- README 副本：[`projects/openvla_train/README.md`](./projects/openvla_train/README.md)
- 简介：该仓库提供一个最小可复现模板，用于在 OpenVLA 基座模型上进行 LoRA 微调。所有脚本默认运行在 conda 创建的 openvla 环境中，无需额外修改环境。

### `openvla_fx`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/openvla_fx`
- 简介：（本地无 README，待补充）

### `openpi`

- GitHub：[Physical-Intelligence/openpi](https://github.com/Physical-Intelligence/openpi)
- 本地路径：`/mnt/ssdmax/openpi`
- README 副本：[`projects/openpi/README.md`](./projects/openpi/README.md)
- 简介：Physical Intelligence 开源机器人模型与工具包（π 系列相关）。

### `InternVLA-A1`

- GitHub：[InternRobotics/InternVLA-A1](https://github.com/InternRobotics/InternVLA-A1)
- 本地路径：`/mnt/ssdmax/InternVLA-A1`
- README 副本：[`projects/InternVLA-A1/README.md`](./projects/InternVLA-A1/README.md)
- 简介：统一场景理解、视觉前瞻与动作执行的 InternVLA-A1 框架。

### `opendm`

- GitHub：[dexmal/opendm](https://github.com/dexmal/opendm)
- 本地路径：`/mnt/ssdmax/opendm`
- README 副本：[`projects/opendm/README.md`](./projects/opendm/README.md)
- 简介：Dexmal 开源具身/数据与模型相关项目（DM 系列）。

### `realtime-vla-flash`

- GitHub：[dexmal/realtime-vla-flash](https://github.com/dexmal/realtime-vla-flash)
- 本地路径：`/mnt/ssdmax/realtime-vla-flash`
- README 副本：[`projects/realtime-vla-flash/README.md`](./projects/realtime-vla-flash/README.md)
- 简介：面向实时推理的 VLA Flash 相关实现。

### `pwm`

- GitHub：[AlayaLab/pwm](https://github.com/AlayaLab/pwm)
- 本地路径：`/mnt/ssdmax/pwm`
- README 副本：[`projects/pwm/README.md`](./projects/pwm/README.md)
- 简介：AlayaLab PWM：机器人策略/世界模型相关项目。

### `egosteer`

- GitHub：[egosteer/egosteer](https://github.com/egosteer/egosteer)
- 本地路径：`/mnt/ssdmax/egosteer`
- README 副本：[`projects/egosteer/README.md`](./projects/egosteer/README.md)
- 简介：EgoSteer：自我中心视角操控/转向相关具身模型。

### `egosmith`

- GitHub：[egosteer/egosmith](https://github.com/egosteer/egosmith)
- 本地路径：`/mnt/ssdmax/egosmith`
- README 副本：[`projects/egosmith/README.md`](./projects/egosmith/README.md)
- 简介：EgoSmith：与 EgoSteer 生态相关的具身智能组件。

### `ReKep`

- GitHub：[huangwl18/ReKep](https://github.com/huangwl18/ReKep)
- 本地路径：`/mnt/ssdmax/ReKep`
- README 副本：[`projects/ReKep/README.md`](./projects/ReKep/README.md)
- 简介：基于关键点/约束的机器人操作规划方法开源实现。

### `vla-data-collect`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/vla-data-collect`
- 简介：（本地无 README，待补充）

## 世界模型

### `cosmos`

- GitHub：[NVIDIA/cosmos](https://github.com/NVIDIA/cosmos)
- 本地路径：`/mnt/ssdmax/cosmos`
- README 副本：[`projects/cosmos/README.md`](./projects/cosmos/README.md)
- 简介：NVIDIA Cosmos：物理世界基础世界模型与仿真相关。

### `jepa-wms`

- GitHub：[facebookresearch/jepa-wms](https://github.com/facebookresearch/jepa-wms)
- 本地路径：`/mnt/ssdmax/jepa-wms`
- README 副本：[`projects/jepa-wms/README.md`](./projects/jepa-wms/README.md)
- 简介：Facebook JEPA 世界模型系列（机器人世界建模）。

### `le-wm`

- GitHub：[lucas-maes/le-wm](https://github.com/lucas-maes/le-wm)
- 本地路径：`/mnt/ssdmax/le-wm`
- README 副本：[`projects/le-wm/README.md`](./projects/le-wm/README.md)
- 简介：Latent Embodied World Model 相关实现。

### `unifolm-world-model-action`

- GitHub：[unitreerobotics/unifolm-world-model-action](https://github.com/unitreerobotics/unifolm-world-model-action)
- 本地路径：`/mnt/ssdmax/unifolm-world-model-action`
- README 副本：[`projects/unifolm-world-model-action/README.md`](./projects/unifolm-world-model-action/README.md)
- 简介：Unitree 世界模型-动作一体化开源项目。

### `RynnWorld-4D`

- GitHub：[alibaba-damo-academy/RynnWorld-4D](https://github.com/alibaba-damo-academy/RynnWorld-4D)
- 本地路径：`/mnt/ssdmax/RynnWorld-4D`
- README 副本：[`projects/RynnWorld-4D/README.md`](./projects/RynnWorld-4D/README.md)
- 简介：阿里达摩院 RynnWorld 4D 世界模型相关。

### `Awesome-World-Model-for-Robotics-Policy`

- GitHub：[NTUMARS/Awesome-World-Model-for-Robotics-Policy](https://github.com/NTUMARS/Awesome-World-Model-for-Robotics-Policy)
- 本地路径：`/mnt/ssdmax/Awesome-World-Model-for-Robotics-Policy`
- README 副本：[`projects/Awesome-World-Model-for-Robotics-Policy/README.md`](./projects/Awesome-World-Model-for-Robotics-Policy/README.md)
- 简介：机器人策略相关世界模型论文/项目精选列表。

### `stable-wm`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/stable-wm`
- 简介：（本地无 README，待补充）

### `LaWAM`

- GitHub：[RLinf/LaWAM](https://github.com/RLinf/LaWAM)
- 本地路径：`/mnt/ssdmax/LaWAM`
- README 副本：[`projects/LaWAM/README.md`](./projects/LaWAM/README.md)
- 简介：世界/动作模型相关开源（RLinf/LaWAM）。

## 操作 / 抓取 / 位姿

### `FoundationPose`

- GitHub：[NVlabs/FoundationPose](https://github.com/NVlabs/FoundationPose)
- 本地路径：`/mnt/ssdmax/FoundationPose`
- README 副本：[`projects/FoundationPose/README.md`](./projects/FoundationPose/README.md)
- 简介：NVIDIA 通用 6D 物体位姿估计与跟踪。

### `OnePoseviaGen`

- GitHub：[GZWSAMA/OnePoseviaGen](https://github.com/GZWSAMA/OnePoseviaGen)
- 本地路径：`/mnt/ssdmax/OnePoseviaGen`
- README 副本：[`projects/OnePoseviaGen/README.md`](./projects/OnePoseviaGen/README.md)
- 简介：One View, Many Worlds: Single-Image to 3D Object Meets Generative Domain Randomization for One-Shot 6D Pose Estimation

### `PVN3D`

- GitHub：[ethnhe/PVN3D](https://github.com/ethnhe/PVN3D)
- 本地路径：`/mnt/ssdmax/PVN3D`
- README 副本：[`projects/PVN3D/README.md`](./projects/PVN3D/README.md)
- 简介：This is the official source code for PVN3D: A Deep Point-wise 3D Keypoints Voting Network for 6DoF Pose Estimation, CVPR 2020. (PDF, Videobilibili, Videoyoutube).

### `SAM-6D`

- GitHub：[JiehongLin/SAM-6D](https://github.com/JiehongLin/SAM-6D)
- 本地路径：`/mnt/ssdmax/SAM-6D`
- README 副本：[`projects/SAM-6D/README.md`](./projects/SAM-6D/README.md)
- 简介：- [2024/03/07] We publish an updated version of our paper on ArXiv. - [2024/02/29] Our paper is accepted by CVPR2024!

### `ggcnn`

- GitHub：[dougsm/ggcnn](https://github.com/dougsm/ggcnn)
- 本地路径：`/mnt/ssdmax/ggcnn`
- README 副本：[`projects/ggcnn/README.md`](./projects/ggcnn/README.md)
- 简介：Note: This is a cleaned-up, PyTorch port of the GG-CNN code. For the original Keras implementation, see the RSS2018 branch. Main changes are major code clean-ups and documentation, an improved GG-CNN2 model, ability to use the Jacquard dataset and simpler evaluation.

### `robotic-grasping`

- GitHub：[skumra/robotic-grasping](https://github.com/skumra/robotic-grasping)
- 本地路径：`/mnt/ssdmax/robotic-grasping`
- README 副本：[`projects/robotic-grasping/README.md`](./projects/robotic-grasping/README.md)
- 简介：We present a novel generative residual convolutional neural network based model architecture which detects objects in the camera’s field of view and predicts a suitable antipodal grasp configuration for the objects in the image.

### `yoloworld_graspnet`

- GitHub：[dehaozhou/Dehao-Zhou](https://github.com/dehaozhou/Dehao-Zhou)
- 本地路径：`/mnt/ssdmax/yoloworld_graspnet`
- README 副本：[`projects/yoloworld_graspnet/README.md`](./projects/yoloworld_graspnet/README.md)
- 简介：该系列代码基于b站分享教学视频开源：https://space.bilibili.com/22108883/lists 如果对您有帮助，麻烦点个star，谢谢！

### `point-to-pose`

- GitHub：[tzuyuan/point-to-pose](https://github.com/tzuyuan/point-to-pose)
- 本地路径：`/mnt/ssdmax/point-to-pose`
- README 副本：[`projects/point-to-pose/README.md`](./projects/point-to-pose/README.md)
- 简介：European Conference on Computer Vision (ECCV) 2026

### `detect_angle`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/detect_angle`
- README 副本：[`projects/detect_angle/README.md`](./projects/detect_angle/README.md)
- 简介：- 使用YOLO模型进行目标检测 - 自动识别框角位置 - 根据框角位置计算旋转角度 - 可视化检测结果和角度信息

### `s2m2`

- GitHub：[junhong-3dv/s2m2](https://github.com/junhong-3dv/s2m2)
- 本地路径：`/mnt/ssdmax/s2m2`
- README 副本：[`projects/s2m2/README.md`](./projects/s2m2/README.md)
- 简介：S 2 M 2 : Scalable Stereo Matching Model for Reliable Depth Estimation (ICCV 2025) Junhong Min¹ , Youngpil Jeon¹, Jimin Kim¹, Minyong Choi¹

## 运动规划 / 控制 / 教材

### `moveit2`

- GitHub：[moveit/moveit2](https://github.com/moveit/moveit2)
- 本地路径：`/mnt/ssdmax/moveit2`
- README 副本：[`projects/moveit2/README.md`](./projects/moveit2/README.md)
- 简介：MoveIt 2：ROS 2 运动规划框架。

### `archify`

- GitHub：[tt-a1i/archify](https://github.com/tt-a1i/archify)
- 本地路径：`/mnt/ssdmax/archify`
- README 副本：[`projects/archify/README.md`](./projects/archify/README.md)
- 简介：Turn a codebase or system description into a polished, interactive system map — directly in chat.

### `Introduction-to-Autonomous-Robots`

- GitHub：[Introduction-to-Autonomous-Robots/Introduction-to-Autonomous-Robots](https://github.com/Introduction-to-Autonomous-Robots/Introduction-to-Autonomous-Robots)
- 本地路径：`/mnt/ssdmax/Introduction-to-Autonomous-Robots`
- README 副本：[`projects/Introduction-to-Autonomous-Robots/README.md`](./projects/Introduction-to-Autonomous-Robots/README.md)
- 简介：《Introduction to Autonomous Robots》开源教材源码。

### `Introduction-to-Autonomous-Robots-zh`

- GitHub：[Introduction-to-Autonomous-Robots/Introduction-to-Autonomous-Robots](https://github.com/Introduction-to-Autonomous-Robots/Introduction-to-Autonomous-Robots)
- 本地路径：`/mnt/ssdmax/Introduction-to-Autonomous-Robots-zh`
- README 副本：[`projects/Introduction-to-Autonomous-Robots-zh/README.md`](./projects/Introduction-to-Autonomous-Robots-zh/README.md)
- 简介：自主机器人导论中文相关材料。

### `Gen2Humanoid`

- GitHub：[RavenLeeANU/Gen2Humanoid](https://github.com/RavenLeeANU/Gen2Humanoid)
- 本地路径：`/mnt/ssdmax/Gen2Humanoid`
- README 副本：[`projects/Gen2Humanoid/README.md`](./projects/Gen2Humanoid/README.md)
- 简介：人形机器人相关生成/控制项目。

### `Xiaomi-Robotics-1`

- GitHub：[XiaomiRobotics/Xiaomi-Robotics-1](https://github.com/XiaomiRobotics/Xiaomi-Robotics-1)
- 本地路径：`/mnt/ssdmax/Xiaomi-Robotics-1`
- README 副本：[`projects/Xiaomi-Robotics-1/README.md`](./projects/Xiaomi-Robotics-1/README.md)
- 简介：小米机器人开源项目。

### `H3`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/H3`
- 简介：（本地无 README，待补充）

## 感知 / SLAM / 三维重建

### `FAST-LIVO2`

- GitHub：[hku-mars/FAST-LIVO2](https://github.com/hku-mars/FAST-LIVO2)
- 本地路径：`/mnt/ssdmax/FAST-LIVO2`
- README 副本：[`projects/FAST-LIVO2/README.md`](./projects/FAST-LIVO2/README.md)
- 简介：HKU-MARS 紧耦合激光-视觉里程计/建图。

### `fast_livo2_ws`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/fast_livo2_ws`
- 简介：（本地无 README，待补充）

### `Fast-FoundationStereo`

- GitHub：[NVlabs/Fast-FoundationStereo](https://github.com/NVlabs/Fast-FoundationStereo)
- 本地路径：`/mnt/ssdmax/Fast-FoundationStereo`
- README 副本：[`projects/Fast-FoundationStereo/README.md`](./projects/Fast-FoundationStereo/README.md)
- 简介：NVIDIA 快速立体匹配/深度基础模型。

### `vggt`

- GitHub：[facebookresearch/vggt](https://github.com/facebookresearch/vggt)
- 本地路径：`/mnt/ssdmax/vggt`
- README 副本：[`projects/vggt/README.md`](./projects/vggt/README.md)
- 简介：Visual Geometry Group, University of Oxford; Meta AI

### `vidmap`

- GitHub：[cvg/vidmap](https://github.com/cvg/vidmap)
- 本地路径：`/mnt/ssdmax/vidmap`
- README 副本：[`projects/vidmap/README.md`](./projects/vidmap/README.md)
- 简介：Exploiting Temporal Structure for Video-Based Structure-from-Motion

### `mapping`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/mapping`
- README 副本：[`projects/mapping/README.md`](./projects/mapping/README.md)
- 简介：复现论文 Mapping Networks：仅训练低维隐向量 z，通过冻结映射矩阵（权重调制）动态生成主干 CNN 全部权重。

### `apriltag`

- GitHub：[AprilRobotics/apriltag](https://github.com/AprilRobotics/apriltag)
- 本地路径：`/mnt/ssdmax/apriltag`
- README 副本：[`projects/apriltag/README.md`](./projects/apriltag/README.md)
- 简介：AprilTag 3 ========== AprilTag is a visual fiducial system popular in robotics research. This repository contains the most recent version of AprilTag, AprilTag 3, which includes a faster (2x) detector, improved detection rate on small tags, flexible tag layouts, and pose estimation. AprilTag consists of a small C library with minimal dependencies.

### `hdl_people_tracking`

- GitHub：[koide3/hdl_people_tracking](https://github.com/koide3/hdl_people_tracking)
- 本地路径：`/mnt/ssdmax/hdl_people_tracking`
- README 副本：[`projects/hdl_people_tracking/README.md`](./projects/hdl_people_tracking/README.md)
- 简介：hdlpeopletracking is a ROS package for real-time people tracking using a 3D LIDAR. It first performs [Haselich's clustering technique][1] to detect human candidate clusters, and then applies [Kidono's person classifier][2] to eliminate false detections. The detected clusters are tracked by using Kalman filter with a contant velocity model.

### `terrain_analysis`

- GitHub：[scorpio-robot/terrain_analysis](https://github.com/scorpio-robot/terrain_analysis)
- 本地路径：`/mnt/ssdmax/terrain_analysis`
- README 副本：[`projects/terrain_analysis/README.md`](./projects/terrain_analysis/README.md)
- 简介：A ROS2 package for real-time terrain analysis using LiDAR point clouds, providing elevation maps for autonomous navigation in complex environments.

### `terrain_analysis_ext`

- GitHub：[scorpio-robot/terrain_analysis_ext](https://github.com/scorpio-robot/terrain_analysis_ext)
- 本地路径：`/mnt/ssdmax/terrain_analysis_ext`
- README 副本：[`projects/terrain_analysis_ext/README.md`](./projects/terrain_analysis_ext/README.md)
- 简介：A ROS2 package for extended-scale terrain analysis, providing enhanced terrain mapping capabilities with larger voxel sizes and advanced connectivity analysis.

### `orb_ws`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/orb_ws`
- 简介：（本地无 README，待补充）

### `orb_cap`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/orb_cap`
- 简介：（本地无 README，待补充）

## 移动机器人 / 真机工程

### `autoware`

- GitHub：[autowarefoundation/autoware](https://github.com/autowarefoundation/autoware)
- 本地路径：`/mnt/ssdmax/autoware`
- README 副本：[`projects/autoware/README.md`](./projects/autoware/README.md)
- 简介：Autoware 自动驾驶开源栈元仓库。

### `autoware.universe`

- GitHub：[autowarefoundation/autoware.universe](https://github.com/autowarefoundation/autoware.universe)
- 本地路径：`/mnt/ssdmax/autoware.universe`
- README 副本：[`projects/autoware.universe/README.md`](./projects/autoware.universe/README.md)
- 简介：Autoware Universe 核心功能包集合。

### `CSRObot428`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/CSRObot428`
- 简介：（本地无 README，待补充）

### `Robot_ws`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/Robot_ws`
- 简介：（本地无 README，待补充）

### `Robot_ws2`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/Robot_ws2`
- 简介：（本地无 README，待补充）

### `robot_waist_rotation`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/robot_waist_rotation`
- README 副本：[`projects/robot_waist_rotation/README.md`](./projects/robot_waist_rotation/README.md)
- 简介：切换是否使用moke ros2 launch moveitconfig demo.launch.py usemockhardware:=true

### `sjrobot`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/sjrobot`
- 简介：（本地无 README，待补充）

### `robo`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/robo`
- 简介：（本地无 README，待补充）

### `robot_for_urdf`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/robot_for_urdf`
- 简介：（本地无 README，待补充）

### `robot_grap`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/robot_grap`
- README 副本：[`projects/robot_grap/README.md`](./projects/robot_grap/README.md)
- 简介：这是一个用于计算机器人手臂抓取动作的Python项目。系统根据物体的位置、位姿和夹爪参数，自动规划机器人的抓取动作序列。

### `waist_carry`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/waist_carry`
- 简介：（本地无 README，待补充）

### `ros2-mcp-server`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/ros2-mcp-server`
- 简介：（本地无 README，待补充）

### `task-bar-pipeline`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/task-bar-pipeline`
- README 副本：[`projects/task-bar-pipeline/README.md`](./projects/task-bar-pipeline/README.md)
- 简介：任务栏串联流水线 MVP：任务按 todo → doing → review → done 顺序推进，不可跳阶段。

### `yolo_e`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/yolo_e`
- README 副本：[`projects/yolo_e/README.md`](./projects/yolo_e/README.md)
- 简介：- 支持 YOLOv5 和 YOLOv8 模型训练 - 自动安装依赖 - 可自动生成数据集配置文件 - 灵活的参数配置

### `yolo_train`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/yolo_train`
- README 副本：[`projects/yolo_train/README.md`](./projects/yolo_train/README.md)
- 简介：- 支持 YOLOv5 和 YOLOv8 模型训练 - 自动安装依赖 - 可自动生成数据集配置文件 - 灵活的参数配置

### `MPP`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/MPP`
- README 副本：[`projects/MPP/README.md`](./projects/MPP/README.md)
- 简介：模参推理（Model Parameter Inference, MPP）算法是一种基于任务语义+视觉特征+人类直觉先验，通过轻量化推理网络自动生成目标模型（如YOLOv11）适配层（如Attention-LoRA）参数的端到端算法。

### `MPP_YOLO`

- GitHub：_本地目录，无 remote_
- 本地路径：`/mnt/ssdmax/MPP_YOLO`
- 简介：（本地无 README，待补充）

