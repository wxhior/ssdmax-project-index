# 机器人抓取规划系统

这是一个用于计算机器人手臂抓取动作的Python项目。系统根据物体的位置、位姿和夹爪参数，自动规划机器人的抓取动作序列。

## 功能特性

- **物体信息输入**：支持输入物体的位置(xyz)、位姿(roll/pitch/yaw)、夹爪抓取角度、宽度和位置偏移
- **逆运动学计算**：自动计算机器人关节角度以达到目标抓取位姿
- **抓取路径规划**：自动规划接近、抓取和后退的完整动作序列
- **可行性验证**：验证抓取动作是否在机器人工作空间内
- **可视化**：提供3D可视化功能，展示抓取路径和机器人配置

## 项目结构

```
robot_grap/
├── robot_grasp/          # 主包
│   ├── __init__.py       # 包初始化
│   ├── object_info.py    # 物体信息模块
│   ├── robot_model.py    # 机器人模型和运动学
│   ├── grasp_planner.py  # 抓取规划器
│   └── visualizer.py     # 可视化模块
├── main.py               # 主程序示例
├── requirements.txt      # 依赖包
└── README.md            # 说明文档
```

## 安装

1. 克隆或下载项目到本地

2. 安装依赖：
```bash
pip install -r requirements.txt
```

## 使用方法

### 基本使用

```python
import numpy as np
from robot_grasp.object_info import ObjectInfo
from robot_grasp.robot_model import RobotConfig
from robot_grasp.grasp_planner import GraspPlanner

# 1. 定义物体信息
object_info = ObjectInfo(
    position=(0.4, 0.2, 0.1),           # 物体位置 (x, y, z) 单位：米
    orientation=(0.0, 0.0, np.pi/4),   # 物体位姿 (roll, pitch, yaw) 单位：弧度
    grasp_angle=np.pi/6,                # 抓取角度 30度
    grasp_width=0.05,                   # 夹爪宽度 5cm
    grasp_offset=(0.0, 0.0, 0.0)       # 夹爪偏移
)

# 2. 配置机器人
robot_config = RobotConfig(
    base_height=0.1,  # 基座高度
)

# 3. 创建规划器并规划抓取
planner = GraspPlanner(robot_config)
sequence = planner.plan_complete_grasp_sequence(object_info)

# 4. 获取关节角度
for step in sequence:
    if step['joint_angles'] is not None:
        print(f"动作: {step['type']}")
        print(f"关节角度: {step['joint_angles']}")
        print(f"夹爪宽度: {step['gripper_width']}")
```

### 运行示例程序

```bash
python main.py
```

这将：
1. 创建一个示例物体
2. 规划抓取动作序列
3. 显示详细的抓取信息
4. 生成可视化图像

## 参数说明

### ObjectInfo 参数

- `position`: 物体位置，元组 (x, y, z)，单位：米
- `orientation`: 物体位姿，元组 (roll, pitch, yaw)，单位：弧度
- `grasp_angle`: 夹爪抓取角度，相对于物体法线的角度，单位：弧度
- `grasp_width`: 夹爪张开宽度，单位：米
- `grasp_offset`: 夹爪相对于物体中心的偏移，元组 (x, y, z)，单位：米

### RobotConfig 参数

- `base_height`: 机器人基座高度，单位：米
- `dh_params`: DH参数列表，格式为 [(a, d, alpha, theta_offset), ...]
- `joint_limits`: 关节角度限制，格式为 [(min, max), ...]，单位：弧度

## 输出说明

抓取规划器返回的动作序列包含以下信息：

- `type`: 动作类型
  - `approach`: 接近物体
  - `grasp`: 到达抓取位置
  - `grasp_close`: 闭合夹爪
  - `retreat`: 后退
- `position`: 末端执行器位置 (x, y, z)
- `rotation`: 末端执行器旋转矩阵 (3x3)
- `joint_angles`: 关节角度数组（弧度）
- `gripper_width`: 夹爪宽度（米）

## 自定义机器人模型

如果需要使用不同的机器人模型，可以修改 `RobotConfig` 的DH参数：

```python
robot_config = RobotConfig(
    base_height=0.1,
    dh_params=[
        (a1, d1, alpha1, theta_offset1),  # 关节1
        (a2, d2, alpha2, theta_offset2),  # 关节2
        # ... 更多关节
    ],
    joint_limits=[
        (min1, max1),  # 关节1限制
        (min2, max2),  # 关节2限制
        # ... 更多关节限制
    ]
)
```

## 依赖包

- numpy: 数值计算
- scipy: 优化算法（用于逆运动学求解）
- matplotlib: 可视化
- transforms3d: 坐标变换（可选）

## 注意事项

1. 逆运动学求解使用数值优化方法，对于复杂配置可能需要调整初始值
2. 默认使用6自由度机械臂模型，可根据实际机器人修改DH参数
3. 关节角度限制需要根据实际机器人设置
4. 抓取可行性验证包括工作空间检查和关节限制检查

## 扩展功能

可以进一步扩展的功能：

- 添加碰撞检测
- 支持多抓取姿态选择
- 添加路径平滑算法
- 支持力控制抓取
- 添加仿真接口（如Gazebo、PyBullet）

## 许可证

本项目仅供学习和研究使用。

