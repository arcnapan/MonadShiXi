# GitHub 探索日志 — Week 2 Challenge.

## 项目 1：Moss — mox 交易安全检查框架

**仓库：** github.com/nishuzumi/moss（37 ⭐，13 Forks）

### 目录结构

```
moss/
├── packages/          # 核心代码，Monorepo 分包
├── docs/              # 文档
├── examples/          # 使用示例
├── .claude/agents/    # Claude Agent 配置文件
├── .github/           # CI/CD 工作流
└── README.md / CLAUDE.md / CONTRIBUTING.md
```

### 各模块作用

| 模块 | 作用 |
|---|---|
| README | 项目定位：Moss 是 Agent 链上交互的安全层，核心流程 discover → load → action → simulate |
| Docs | 含 ADR（架构决策记录），解释了设计取舍 |
| Issues | 早期阶段，issue 较少，集中在协议适配请求 |
| Pull Requests | 小团队维护，PR 规模小，review 密集 |
| MCP 配置 | 作为 MCP Server 暴露 4 个工具给 Agent 调用 |

### 我感兴趣的 Issue/功能

Moss 当前只支持 Monad 链，我感兴趣的其实是它 **多链适配的路线图**。在现实场景中，Agent 需要跨链操作（比如在 Monad 发现收益机会，但资金在 Base 上）。当前的架构抽象层如果能扩展到多链，Moss 的价值会翻倍。

---

## 我的发现与收获

**1. 项目组织的成熟度差异很明显。**
Moss 作为刚发布的 Alpha 项目，结构简洁但核心概念文档（ADR）已经建立——这说明小项目也要从第一天就把架构决策写清楚。

**2. AI 辅助开发正在改变开源项目的组织方式。**
Moss 有 CLAUDE.md + .mcp.json。传统项目只有给人类读的 CONTRIBUTING.md，现在开始多了给 AI 读的指引文件。这个变化可能比我们想象的更快——未来维护一个开源项目可能越来越依赖维护者同时管理「人类贡献者」和「AI 贡献者」两条线。

**3. PR / Issue 的标签体系是了解项目健康度的入口。**
Moss 虽然才 37 star 但已经建立了 issue 模板和 ADR 文档。早期能不能活下来，有时候不在于代码多完美，而在于基础设施（CI/文档/社区规范）有没有在一开始就搭好。
