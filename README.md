# 稳健理财研究助手 (steady-investment-advisor)

一个给 Claude 用的插件：把你关心的理财产品（基金、银行理财、货币基金、债券、大额存单等）整理成**结构化的评估卡**和**对比表**，聚焦**低风险、短期限、流动性**，并把风险点讲清楚。

它的定位是**信息整理工具**，不是荐股/荐基工具——它帮你把事实摆清楚、把权衡讲明白，决定权始终在你手里。

## 它能做什么

- 把一款产品整理成一张**评估卡**：类型、风险等级、期限、流动性、费用、底层资产、历史波动、主要风险点。
- 把多款产品放进统一口径的**对比表**，一眼看出关键差异；也可用斜杠命令 `/理财对比 <产品...>` 一键触发。
- 解释概念问题：R1–R5 风险等级、货币基金会否亏损、银行理财与存款的区别等。
- 主动提示**红旗信号**（如宣称保本保收益、费率与口头承诺不符等）。
- 附一份可填写的 **Excel 模板**（评估卡 + 对比表两个工作表），方便导出留存和长期跟踪。

## 它不会做什么

- 不推荐具体产品、不预测收益、不承诺保本。
- 不替代持牌投资顾问。所有输出都附带风险提示。

## 安装

### 方式一：直接安装

```bash
claude plugin install muguang1224/steady-investment-advisor
```

安装后即可唤起技能，例如输入"帮我评估一下这只货币基金"，或使用 `/理财对比` 命令。

### 方式二：作为插件市场安装

本仓库同时是一个插件市场（`muguang-plugins`），可以这样添加后安装：

```bash
claude plugin marketplace add muguang1224/steady-investment-advisor
claude plugin install steady-investment-advisor@muguang-plugins
```

### 方式三：本地试用

```bash
git clone https://github.com/muguang1224/steady-investment-advisor.git
claude --plugin-dir ./steady-investment-advisor
```

## 使用示例

- 「帮我对比一下这两只短债基金：××× 和 ×××」
- 「这个银行理财 R2，3 个月封闭，会亏吗？」
- 「我有一笔钱 6 个月后要用，放货币基金还是大额存单？」
- 「R3 和中低风险是一回事吗？」
- `/理财对比 ×××货币基金 ×××短债基金 ×××大额存单`

技能会被自动触发；也可以直接用斜杠命令 `/理财对比` 带上要对比的产品。

## 目录结构

```
steady-investment-advisor/
├── .claude-plugin/
│   ├── plugin.json                       # 插件清单
│   └── marketplace.json                  # 插件市场清单（muguang-plugins）
├── commands/
│   └── 理财对比.md                        # /理财对比 斜杠命令
├── skills/
│   └── steady-investment-advisor/
│       ├── SKILL.md                      # 技能定义
│       └── assets/
│           └── 评估卡模板.xlsx             # 可填写的评估卡 / 对比表模板
├── README.md
└── LICENSE
```

## 免责声明

本插件输出的内容只是对公开信息的结构化整理，**不构成投资建议**。理财产品不保本，历史业绩不代表未来表现，请以产品官方说明书和合同为准。使用前请结合自身风险承受能力独立判断，必要时咨询持牌专业人士。

## 许可

MIT License，详见 [LICENSE](LICENSE)。
