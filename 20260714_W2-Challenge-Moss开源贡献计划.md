# Moss 开源贡献计划 — Ops Builder

## Builder 身份

**Ops Builder**，主攻内容创作与开发者体验方向。

## 贡献方向

完善 Moss 的 README 中文版 + 编写面向 Agent 开发者的 Tutorial。

## 为什么选择这个方向

Moss 目前的中文文档存在几个问题：

1. README.zh-CN.md 明确标注了「中文文档可能滞后于英文版；以英文版为准」，说明中文文档长期未维护。
2. 项目目前只有英文 README 和中文 README 两篇文档，缺乏面向不同角色（Agent 开发者 / DApp 接入方 / 普通用户）的分层教程。
3. Moss 作为一个面向 Agent 的框架，它的核心价值在于「降低 Agent 链上交互的安全风险」，但这个价值在当前的 README 里表达得偏技术，普通用户或 Ops 方向的同学看完不一定能立刻理解自己能怎么用。

作为 Ops Builder，我可以补的是：**架起 Moss 核心能力和使用者之间的文档桥梁**。不修改代码，而是让更多人看懂、能用、愿意尝试。

---

## 本周目标

### 目标 1：更新中文 README

**现状：** README.zh-CN.md 标注为滞后版本，翻译不完全、缺乏使用示例。

**计划做的事情：**

- 对照英文 README 逐段审核，补全缺失的翻译内容。
- 在中文版开头加一段「Moss 解决什么问题」的人话版说明（200 字以内），让零基础读者也能快速理解。
- 在 README 末尾加一个「Qucik Start」的简化版步骤，把从安装到跑通第一个 Plan 的流程压缩成 5 步。

**预计产出：** 一份与英文版同步的中文 README，语言风格从技术文档调整为面向 Agent 开发者的实践指南。

### 目标 2：写一篇 Tutorial — 「5 分钟让 Agent 安全调用 Monad DEX」

**现状：** Moss 仓库里有 `examples/` 目录但缺少配套的教程说明。开发者不知道这些 example 怎么跑、跑起来之后能看到什么、怎么验证结果是对的。

**计划做的事情：**

基于 Moss 官方 example（Kuru DEX swap）写一篇教程，包含：

- 环境准备（Node.js 版本、Moss 安装、MCP Server 启动）。
- 分步说明：discover → load → action → simulate 四步的代码和输出。
- 每一步之后说明：这一步发生了什么、出现了什么问题的话可能是哪里错了。
- 结尾加一个「常见问题」章节，覆盖新手最容易卡住的点（比如 simulate 失败的原因、Plan 格式写错的提示）。

**预计产出：** 一篇 Tutorial.md，可直接提交 PR 到 Moss 仓库的 `docs/` 目录。

---

## 完成计划

| 日期 | 事项 |
|---|---|
| Day 1 | 在本地完整跑通 Moss 的 example（Kuru DEX swap），记录每一步的输出和可能的错误 |
| Day 2 | 基于运行记录撰写 Tutorial 初稿 |
| Day 3 | 对照英文 README 更新中文 README，提交 Draft PR |
| Day 4 | 根据 maintainer 反馈修改，合并 PR |

---

## 预计产出清单

| 产出 | 格式 | 目标 |
|---|---|---|
| 更新后中文 README | PR → moss 仓库 | 与英文版同步，补充人话版简介 |
| Tutorial：5 分钟让 Agent 安全调用 Monad DEX | PR → moss/docs/ | Step-by-step 教程，降低上手门槛 |

---


