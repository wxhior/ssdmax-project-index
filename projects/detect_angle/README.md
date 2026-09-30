# 旋转角度检测程序

通过YOLO模型检测框角位置，并根据框角位置计算旋转角度。

## 功能特点

- 使用YOLO模型进行目标检测
- 自动识别框角位置
- 根据框角位置计算旋转角度
- 可视化检测结果和角度信息

## 安装依赖

```bash
pip install -r requirements.txt
```

## 使用方法

### 基本用法

```bash
python detect_angle.py --image <图像路径> --model best.pt
```

### 完整参数

```bash
python detect_angle.py \
    --image <图像路径> \
    --model best.pt \
    --conf 0.25 \
    --output <输出图像路径> \
    --show
```

### 参数说明

- `--image`: 输入图像路径（必需）
- `--model`: YOLO模型路径（默认: best.pt）
- `--conf`: 置信度阈值（默认: 0.25）
- `--output`: 输出图像路径（可选）
- `--show`: 显示结果图像窗口

## 示例

```bash
# 检测图像并显示结果
python detect_angle.py --image test.jpg --show

# 检测图像并保存结果
python detect_angle.py --image test.jpg --output result.jpg

# 使用自定义置信度阈值
python detect_angle.py --image test.jpg --conf 0.5 --show
```

## 输出说明

程序会输出：
- 检测到的目标数量
- 每个目标的置信度
- 计算得到的旋转角度（度）
- 边界框坐标
- 各个角点的位置坐标

可视化图像中会显示：
- 绿色边界框
- 红色角点标记
- 角度信息文本
- 角度指示线（紫色）

## 角度计算原理

程序通过以下步骤计算旋转角度：

1. 识别检测框的四个角点
2. 找到最上方的两个角点
3. 计算这两个角点连线与水平线的夹角
4. 将角度归一化到 -90° 到 90° 范围

