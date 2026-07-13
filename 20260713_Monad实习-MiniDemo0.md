# Mini Demo 0 — SimpleMessageBoard on Monad Testnet

## 1. 作品信息
![[Pasted image 20260713204352.png]]

| 项目 | 内容 |
|---|---|
| **合约** | SimpleMessageBoard.sol（链上留言板） |
| **网络** | Monad Testnet |
| **合约地址** | [`0x62C0de0251DD31Ac1b6cc21716b9316c49767611`](https://testnet.monadexplorer.com/address/0x62C0de0251DD31Ac1b6cc21716b9316c49767611) |
| **部署 TxHash** | [`0x195a5089ad93f97c594ebbef26f82ce6aa065f8a77868e2cdf4ccee08bccf51c`](https://testnet.monadexplorer.com/tx/0x195a5089ad93f97c594ebbef26f82ce6aa065f8a77868e2cdf4ccee08bccf51c) |
| **部署钱包** | `0xfdbb97ba3603b478d137a9c8c76845a850aa964c` |
| **状态** | ✅ 确认（Block #43,006,867，Status: Success） |

---

## 2. 做了什么

### 2.1 写了一个 Solidity 合约

SimpleMessageBoard — 最小链上留言板，功能：

- **postMessage(string)** — 发布一条留言，gas 费几乎为零
- **getMessage(uint256)** — 按索引获取留言内容（发送者、内容、时间戳）
- **getMessageCount()** — 查看总留言数

### 2.2 部署到 Monad Testnet

通过 Remix + Rabby 完成编译和部署，链上确认成功

---

## 3. 哪部分是真实链上操作

| 操作          | 说明                                        |
| ----------- | ----------------------------------------- |
| 创建 Rabby 钱包 | 手动设置，切换到 Monad Testnet（Chain ID: 10143）   |
| Faucet 领水   | 通过 https://faucet.monad.xyz 领取测试 MON      |
| Remix 编译    | 上传 .sol 文件 → 选择 Solidity 0.8.20+ → 编译     |
| 部署合约        | 连接 MetaMask → Deploy → 签名交易 → 链上确认        |
| 验证          | 在 testnet.monadexplorer.com 查合约地址和 TxHash |

---

## 4. 哪部分由 AI 辅助完成

| 环节 | AI（Grok）做了什么 |
|---|---|
| 合约初稿 | 根据 Prompt「写一个最小留言板合约」生成初版代码 |
| 合约解释 | 逐行解释 struct / event / function 的作用 |
| 错误修复 | 指出缺少 require、event 无 indexed、命名问题 |
| 部署流程 | 提供 Remix 部署的 7 步流程图 |
| README 模板 | 生成 v0.1 README 占位模板 |

---

## 5. 人工判断和修改（5 个关键点）

| # | AI 初稿问题 | 人工修改 | 理由 |
|---|---|---|---|
| 1 | 无输入验证 | 添加 `require(bytes(_content).length > 0)` | 用户可以发空消息，浪费 gas 且无意义 |
| 2 | event 无 indexed | 给 `sender` 字段加 `indexed` | 前端按地址过滤时效率完全不同 |
| 3 | 无边界检查 | 添加 `require(_index < messages.length)` + 错误信息 | 读取越界索引直接 panic |
| 4 | 函数可见性未优化 | `external` + `calldata` 替代 `public` + `memory` | gas 更低，参数直接读 calldata |
| 5 | 无注释/不规范 | SPDX license + NatSpec + 语义化命名 | 专业度、链上可读性 |

**核心判断**：AI 生成的合约在「功能正确」层面合格，但在「安全、gas 优化、专业标准」层面需要人工把关。这 5 个修改点中，每一点都不是 AI 做不到，而是 AI 不会默认做——取决于你怎么写 Prompt

---

## 6. 方向选择

### Ops 为主，Research 辅助

**理由**：

Week 1 写 Solidity 合约 + 部署的经历不是为了转 Tech，而是为了：
- Ops 方向需要理解技术细节才能做出可信的内容
- 只有亲手部署过合约的人，写「Monad 性能有多好」才是真的，不是搬运文档
- Research 分析生态项目时，能看懂合约层面的事情，不会被忽悠

**Week 2 目标**：
- Ops 主产出：1 篇 Monad 生态相关的 X Thread / 长文
- Research 辅助：为每篇内容做调研支撑
- 如果时间充裕，把 SimpleMessageBoard 加个前端做成一个真正能玩的 Mini DApp，作为 Ops 传播素材

---

## 7. 一句话简历写法

> "在 Monad Testnet 上独立完成 Solidity 合约的 AI 辅助开发、人工代码审查和链上部署，熟悉从 Prompt 到链上确认的完整开发流程"


---

## 8. Week 2 想继续推进的问题

1. **Monad 生态中目前最值得做 Ops 传播的项目有哪些？** 想挑 2-3 个做深度内容
2. **Ops 方向的内容传播效果如何量化？** 阅读量 / 互动率 / 社区反馈有没有考核标准
3. **能否拿到 Monad 官方 Discord/Telegram 的入口？** 想加入社区感受氛围
4. **有没有 Ops 方向的参考案例？** 之前 Monad 社区有哪些内容/活动效果比较好的，可以学习

---

