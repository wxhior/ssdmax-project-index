# Mapping Networks 复现 (arXiv:2602.19134)

复现论文 [Mapping Networks](https://arxiv.org/abs/2602.19134)：仅训练低维隐向量 `z`，通过**冻结**映射矩阵（权重调制）动态生成主干 CNN 全部权重。

## 核心公式

```
w_ij ← w_ij + α z_i          # 映射权重调制（W0 冻结）
θ̂ = s · σ(W_mod · z + b)     # 生成扁平化主干参数
W^{(l)}, b^{(l)} = reshape(θ̂)
L_map = L_task + λ_st L_stab + λ_sm L_smooth + λ_al L_align
```

## 环境（uv + RTX 50xx / sm_120）

本机 Blackwell GPU 需要 **PyTorch ≥ 2.7 + CUDA 12.8**：

```bash
cd /mnt/ssdmax/mapping
bash scripts/setup_uv.sh
# 或手动：
# uv venv --python 3.10
# uv pip install .wheels/torch-2.7.1+cu128-*.whl .wheels/torchvision-0.22.1+cu128-*.whl
# uv pip install matplotlib scikit-learn tqdm pyyaml rich
# uv pip install -e . --no-deps
```

验证：

```bash
.venv/bin/python scripts/smoke_test.py
```

## 训练

```bash
# 基线 CNN2（~108K 参数）
.venv/bin/python scripts/train.py --mode baseline --backbone cnn2 --dataset mnist --epochs 5 --lr 0.001

# Layer-wise（推荐，论文 Ours†）
.venv/bin/python scripts/train.py --mode lwt --backbone cnn2 --layer-latent-dim 256 --dataset mnist --epochs 10 --lr 0.03

# Single Latent（论文 Ours*）
.venv/bin/python scripts/train.py --mode slvt --backbone cnn2 --latent-dim 1024 --dataset mnist --epochs 10 --lr 0.05 --residual --no-mapping-loss

# FashionMNIST
.venv/bin/python scripts/train.py --mode lwt --backbone cnn2 --layer-latent-dim 256 --dataset fmnist --epochs 15 --lr 0.03
```

## 参数流形可视化（论文 Fig.2）

```bash
.venv/bin/python scripts/visualize_manifold.py --steps 150 --output outputs/param_manifold.png
```

## 本机实测（MNIST, CNN2≈107,706）

| Method | Trainable | Epochs | Best Acc |
|--------|-----------|--------|----------|
| Baseline CNN2 | 107,706 | 5 | **99.04%** |
| Ours† LWT | 2,048 | 10 | **90.15%** |
| Ours* SLVT | 1,024 | 10 | 52.29% |

LWT 约 **53×** 可训练参数压缩，5–10 epoch 即可到 ~90%；继续加长训练 / 调 `layer-latent-dim` 可进一步逼近论文 Table 1（98%+）。论文附录结构未公开，CNN1/CNN2 为按参数量对齐的近似实现。

## 项目结构

```
src/mapping_networks/
  models/target_cnn.py   # CNN1(~538K) / CNN2(~108K) + functional forward
  models/mapping.py      # SLVT / LWT Mapping Network
  loss.py                # Mapping Loss
  train.py / data.py / viz.py
scripts/
  setup_uv.sh / train.py / smoke_test.py / visualize_manifold.py
```
