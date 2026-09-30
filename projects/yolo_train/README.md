# YOLO 训练脚本使用说明

这个脚本支持训练 YOLOv5 和 YOLOv8 模型。

## 功能特点

- 支持 YOLOv5 和 YOLOv8 模型训练
- 自动安装依赖
- 可自动生成数据集配置文件
- 灵活的参数配置

## 使用方法

### 基本用法

```bash
# 训练 YOLOv8 模型（默认）
python train_yolo.py --data path/to/dataset.yaml

# 训练 YOLOv5 模型
python train_yolo.py --version v5 --data path/to/dataset.yaml

# 指定预训练模型
python train_yolo.py --model yolov8m.pt --data path/to/dataset.yaml

# 设置训练参数
python train_yolo.py --epochs 50 --batch-size 32 --img-size 640 --data path/to/dataset.yaml
```

### 参数说明

- `--version` 或 `-v`: YOLO 版本，可选 `v5` 或 `v8`（默认）
- `--model`: 预训练模型路径或名称（默认：yolov8s.pt）
- `--data`: 数据集配置文件路径（必需）
- `--epochs`: 训练轮数（默认：100）
- `--batch-size`: 批处理大小（默认：16）
- `--img-size`: 图像尺寸（默认：640）
- `--project`: 训练结果保存目录（默认：runs/train）
- `--name`: 实验名称（默认：exp）
- `--dataset-path`: 数据集路径（配合 --classes 使用可自动生成配置文件）
- `--classes`: 类别名称列表（配合 --dataset-path 使用）

### 自动生成数据集配置文件

如果您的数据集已经按照标准格式组织，可以使用以下方式自动生成配置文件：

```bash
python train_yolo.py \
  --dataset-path /path/to/dataset \
  --classes cat dog person car \
  --data dummy.yaml
```

这将在 `/path/to/dataset` 目录下生成 `dataset.yaml` 文件。

## 数据集格式要求

推荐的数据集组织结构：
```
dataset/
├── images/
│   ├── train/
│   └── val/
└── labels/
    ├── train/
    └── val/
```

## 安装依赖

脚本会自动安装必要的依赖项，但您也可以手动安装：

```bash
# 安装 PyTorch (根据您的系统选择合适的版本)
pip install torch torchvision

# 安装 YOLOv8 依赖
pip install ultralytics

# 安装 YOLOv5 依赖 (如果使用 YOLOv5)
git clone https://github.com/ultralytics/yolov5
cd yolov5
pip install -r requirements.txt
```

## 训练结果

训练结果将保存在指定的 `project/name` 目录中，默认为 `runs/train/exp`。