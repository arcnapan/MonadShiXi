# Week 2 Role Log — Ops

## 基本信息

| 项目 | 内容 |
|---|---|
| 方向 | Ops |
| 时间 | 2026/7/14 — Week 2 |
| 链上记录 | https://github.com/arcnapan/MonadShiXi |

## 本周日志

### 7月14日（Day 1）

**完成：**
- 提交 Week 2 方向确认 + 产出计划（Role Choice Card）
- 简历修改：删除照片/非必要课程内容，新增德业海外技术支持经历，新增 Web3 项目经历和 Monad 实训记录
- 完成自我评价重构
- 调研 Magic Resume（magicv.art）简历工具，8.8k ⭐ 开源项目

**资料链接：**
- Magic Resume：https://github.com/JOYCEQL/magic-resume
- 简历文档：`内容创作/研报/Pan-Web3简历-v1.md`

**Prompt 记录：**
- 简历改写使用 Hermes Agent，主要调整方向：从嵌入式技术向 Web3 Ops/内容方向转型
- 核心修改决策：删掉嵌入式具体项目（BMS/无人机/智能车），保留社群管理/多语种/工单闭环等可迁移能力

**判断变化：**
- 此前不确定简历里嵌入式的经历要不要留，改完后更清晰——Ops 方向不需要展示 STM32 或 RTOS 能力，社群规模和多语种沟通才是适配 Web3 Ops 的信号
- 自我评价从能力清单改为段落式自述，读起来更像一个真实的人

**下一步计划：**
- 选定 1 个 Monad 生态项目做深度拆解（TODO: 确定选题）
- 完成封面图风格确认（A3 / 知识图谱科普类方向待定）
- 保持每日记录

---

### （后续日期按此格式扩展）

## 资源收集

| 资源 | 链接 | 用途 |
|---|---|---|
| Monad 文档 | https://docs.monad.xyz | 技术参考 |
| Monad Testnet Explorer | https://testnet.monadexplorer.com | 链上验证 |
| Magic Resume | https://magicv.art | 简历制作 |
| pan-ip-illustrations skill | D:/hermes/skills/pan-ip-illustrations/ | 封面/配图生成 |

## 错误 & 修复记录

| 日期 | 问题 | 修复 |
|---|---|---|
| 7/13 | Qwen-Image 生图偏日系平滑，达不到粗线条涂鸦 | 确认 API 模型上限，后续封面走 Grok |
| 7/13 | 误将知识库根目录 init git 并推到 MonadShiXi | 删除 .git 重建干净仓库 |
| 7/13 | 往知识库写文件未先询问用户 | 记入 memory：必须先问再写 |
| 7/14 | 试读旧简历 PDF 时二进制解析失败 | 改用 pymupdf（安装卡顿），后续用用户直接提供的信息 | 

## 本周最小产出追踪

| 项目 | 状态 |
|---|---|
| Monad 生态项目深度拆解 × 1 | 🔲 |
| 对应 X Thread | 🔲 |
| Ops 工作流 SOP | 🔲 |
| Week 1 Build Log + Mini Demo 0 | ✅ 已完成提交 |
| Role Choice Card | ✅ 已完成提交 |
