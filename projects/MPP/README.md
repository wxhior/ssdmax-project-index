# 模参推理（MPP）算法实现

## 项目简介

模参推理（Model Parameter Inference, MPP）算法是一种基于任务语义+视觉特征+人类直觉先验，通过轻量化推理网络自动生成目标模型（如YOLOv11）适配层（如Attention-LoRA）参数的端到端算法。

## 核心特性

- **跨模态输入**：支持文本描述+图像示例的联合输入
- **直觉库引导**：基于人类认知先验的结构化编码
- **思维链推理**：通过Transformer实现显式推理过程
- **轻量化部署**：Transformer核心仅8M参量，部署友好
- **端到端训练**：从跨模态输入到LoRA参数生成的完整流程

## 项目结构

```
MPP/
├── mpp/
│   ├── model/              # 核心模型模块
│   │   ├── __init__.py
│   │   ├── mpp_model.py    # MPP主模型
│   │   ├── cross_modal_fusion.py  # 跨模态融合模块
│   │   ├── transformer_core.py    # Transformer推理核心
│   │   ├── lora_layers.py         # LoRA参数输出和适配层
│   │   └── intuition_library.py   # 直觉库模块
│   ├── optimizer/          # 优化器
│   │   ├── __init__.py
│   │   └── musgd.py        # MuSGD优化器
│   ├── utils/              # 工具函数
│   │   ├── __init__.py
│   │   ├── losses.py       # 损失函数（CIoU+分类损失）
│   │   ├── data_utils.py   # 数据工具函数
│   │   └── yolo_integration.py  # YOLOv11集成
│   └── train.py            # 训练脚本
├── configs/                # 配置文件
│   └── default_config.json
└── README.md
```

## 核心模块说明

### 1. MPPModel（主模型）
- **功能**：完整的模参推理流程
- **输入**：文本特征（768维）+ 图像特征（512维）
- **输出**：Attention-LoRA参数（A矩阵、B矩阵、注意力权重α）

### 2. CrossModalFusion（跨模态融合）
- **功能**：通过Cross-Attention实现文本语义与图像特征的精准对齐
- **架构**：文本为Query，图像为Key/Value

### 3. TransformerCore（推理核心）
- **功能**：轻量化Encoder-only结构，支持思维链序列推理
- **参数**：6层，8头注意力，8M参量

### 4. IntuitionLibrary（直觉库）
- **功能**：人类认知先验的结构化编码
- **类型**：目标特征直觉、场景干扰直觉、任务适配直觉

### 5. LoRAParamHead（参数输出层）
- **功能**：生成Attention-LoRA完整参数
- **输出**：A矩阵（512×8）、B矩阵（8×512）、注意力权重α（512维）

### 6. MuSGD（优化器）
- **功能**：多动量动态切换优化器
- **特性**：分模块梯度裁剪，适配Transformer+LoRA混合训练

## 安装依赖

```bash
pip install torch torchvision
pip install transformers  # 用于CLIP文本编码器
pip install ultralytics   # 用于YOLOv11（如果使用）
```

## 使用方法

### 1. 基本使用

```python
import torch
from mpp.model import MPPModel

# 创建模型
model = MPPModel(
    text_dim=768,
    img_dim=512,
    d_model=768,
    nhead=8,
    num_layers=6,
    lora_rank=8
)

# 准备输入（需要先通过CLIP和YOLOv11提取特征）
text_feat = torch.randn(1, 768)  # [B, 768] 文本特征
img_feat = torch.randn(1, 512)   # [B, 512] 图像特征

# 生成LoRA参数
lora_params = model(text_feat, img_feat)
# 返回: {"lora_A": [B, 512, 8], "lora_B": [B, 8, 512], "attn_weight": [B, 512]}
```

### 2. 训练模型

```bash
python -m mpp.train --config configs/default_config.json
```

### 3. 配置文件说明

配置文件`configs/default_config.json`包含以下主要参数：

- **model**：模型架构参数（维度、层数、注意力头数等）
- **optimizer**：优化器参数（学习率、动量、梯度裁剪等）
- **loss**：损失函数权重
- **training**：训练参数（批次大小、轮数等）
- **data**：数据路径配置

## 核心流程

```
【输入层】任务文本描述 + 1~5张示例图像
       ↓
【特征编码层】
  - 文本特征：CLIP-Text Encoder（768维）
  - 图像特征：YOLOv11 Backbone（512维）
       ↓
【跨模态融合层】Cross-Attention对齐语义与视觉特征
       ↓
【直觉引导层】直觉库Token嵌入拼接
       ↓
【Transformer推理核心】思维链序列推理
       ↓
【参数输出层】生成Attention-LoRA完整参数
       ↓
【目标模型适配】注入YOLOv11主干 → 目标检测推理
```

## 注意事项

1. **CLIP和YOLOv11集成**：当前代码中的CLIP和YOLOv11加载部分为占位符，实际使用时需要根据具体的模型实现进行调整。

2. **数据格式**：训练数据需要包含文本描述、图像列表和目标标注（边界框和类别）。

3. **YOLOv11集成**：`yolo_integration.py`中的LoRA注入逻辑需要根据YOLOv11的实际架构进行调整。

4. **设备支持**：代码默认支持CUDA，如果没有GPU会自动使用CPU。

## 开发计划

- [ ] 完善CLIP和YOLOv11的集成
- [ ] 添加数据加载器实现
- [ ] 添加验证和测试脚本
- [ ] 添加可视化工具
- [ ] 优化显存占用

## 许可证

本项目遵循MIT许可证。

## 作者

MPP Algorithm Implementation