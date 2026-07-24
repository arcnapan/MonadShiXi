# Moss 开源项目调研 — Week 2 Challenge

## 项目简介

Moss 是一个基于 Monad 链的 Agent 交易安全框架，由 nishuzumi 开发。它把 Monad 上复杂的 DApp/协议交互（比如 DEX 兑换、代币转账、DeFi 操作）抽象成 Agent 可调用的标准化能力，核心流程是 `discover → load → action → simulate`，由系统而不是 Agent 组装正确的交易

## 核心问题

AI Agent 在链上交互时最大的问题是：**手搓 calldata 容易出错**

一个简单的 DEX swap 就涉及 router 地址、exact-in/exact-out 两种模式、原生代币包装和解包装、slippage 换算、扫尾调用等一堆细节。Agent 靠读 ABI 来组交易，迟早会在某个细节上出问题——而"几乎正确"的交易就是丢钱的方式

## 核心能力

- **统一能力层**：Agent 不再碰 ABI/合约地址/decimals，能力接受人类可读参数，返回组装好的未签名交易
- **Plan + Simulate 双重验证**：Plan 精确声明允许移动的资产（expects），模拟在真实链上状态回放它，未声明的差异直接告警
- **永不签名永不发送**：Moss 只构建和验证，私钥留在钱包里，最终决定权在用户手里
- **MCP Server**：作为 MCP Server 运行，Agent 通过 4 个工具（discover/load/action/simulate）就能与链交互
- **已有协议适配**：WMON、ERC20、ERC721、Kuru DEX（Monad CLOB），一个协议一个包

## 我的理解（200字）

Moss 解决的是 AI Agent 与区块链交互时的信任问题。Agent 自主发交易的核心矛盾在于：Agent 能跑但不能签名，人能签名但看不懂每笔 calldata 的细节。Moss 的方案是用 Plan + Simulation 在签名前加一道机械安全门——不是让 Agent 更聪明，而是让它的每一次操作都必须被验证。对我来说最直观的场景是：在 Monad 训练营里写合约部署和测试时，如果能用 Moss 先模拟再签名，至少能少翻几次车。未来如果 Moss 覆盖的协议更多了，可以做成 Agent 自动投喂策略的入口——Agent 发现一个收益机会，用 Moss 组交易、模拟、确认，人只负责最后签个字。不过目前还在 Alpha，协议覆盖很少，离生产还有距离

## 可能应用场景

1. **DeFi 策略自动化**：Agent 发现套利/做市机会 → Moss 组交易 → 模拟验证 → 钱包确认，人只负责签最后一笔
2. **Monad 生态 DApp 的安全交互层**：用户通过自然语言告诉 Agent "把 100 MON 换成 USDC"，Agent 走 Moss 组交易+模拟，用户确认后签名
3. **Agent 驱动的投喂策略基础设施**：当 Moss 覆盖更多协议后，Agent 可以自行发现收益机会、组交易、模拟、并推送签名请求给用户
4. **学习和调试工具**：新手在模拟环境中跑 Moss，理解每笔交易的实际效果，零成本零风险

---

**GitHub 用户主页：** https://github.com/arcnapan

**已 Star 截图：** ⚠️ 请在浏览器打开 https://github.com/nishuzumi/moss 点击 Star 按钮后截图，补到此处
