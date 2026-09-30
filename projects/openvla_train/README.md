# OpenVLA LoRA 微调项目

该仓库提供一个最小可复现模板，用于在 OpenVLA 基座模型上进行 LoRA 微调。所有脚本默认运行在 `conda` 创建的 `openvla` 环境中，无需额外修改环境。

## 目录结构

- `configs/`：训练配置（YAML）
- `data/`：示例数据存放路径，需自行准备 `train.jsonl` / `val.jsonl`
- `scripts/`：训练脚本、启动脚本
- `src/openvla_train/`：核心 Python 包
- `checkpoints/`、`logs/`：默认输出路径

## 准备数据

数据格式为 JSON Lines，每行包含：

```json
{
  "instruction": "文字指令",
  "response": "期望回答",
  "image": "相对或绝对图像路径"
}
```

将训练/验证集分别保存至 `data/train.jsonl` 与 `data/val.jsonl`（路径可在配置文件中调整）。

## 运行

```bash
cd /home/lwx/openvla_train
conda activate openvla
bash scripts/run_train.sh configs/train_lora.yaml
```

或直接：

```bash
python scripts/train_lora.py --config configs/train_lora.yaml
```

## 自定义

- 修改 `configs/train_lora.yaml` 中的 LoRA、优化器及训练超参。
- 根据硬件情况调整 `batch_size`、`gradient_accumulation_steps` 与 `mixed_precision`。
- 若需要自定义数据预处理，可扩展 `src/openvla_train/data.py`。

