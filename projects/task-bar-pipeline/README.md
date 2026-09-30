# task-bar-pipeline

任务栏串联流水线 MVP：任务按 `todo → doing → review → done` 顺序推进，不可跳阶段。

## 快速开始

```bash
cd /mnt/ssdmax/task-bar-pipeline
npm install
npm test
npm run dev
```

## 文档

- [docs/spec.md](docs/spec.md) — 规格说明
- [docs/plan.md](docs/plan.md) — 实现计划

## 当前进度

- [x] 流水线状态机 + 单元测试
- [x] Task Store + 持久化
- [x] TaskBar UI + 创建/推进交互
- [ ] E2E、更多 polish
