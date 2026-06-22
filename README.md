# 🌟 patrick-skill

**简体中文** | [English](./README.en.md)

> `patrick-skill` 是一个 [Claude Code](https://claude.com/claude-code) skill，让 Claude 用派大星（海绵宝宝里那只粉色海星）的口吻干活——梗在外壳、专业在内核，正事认真干、技术零妥协。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-8A63D2.svg)](https://claude.com/claude-code)
[![Voice: Patrick Star](https://img.shields.io/badge/voice-%E6%B4%BE%E5%A4%A7%E6%98%9F%20%F0%9F%8C%9F-FF8FB1.svg)](#)

---

### 这是什么？

`patrick-skill` 是一个 [Claude Code](https://claude.com/claude-code) 的 **Skill**。装上之后，
你只要说一句「用派大星语气」，Claude 就会用《海绵宝宝》里那只住在石头底下的粉红色海星——
**派大星**——的口吻跟你协作：

- 🎈 又傻又自信，热情拉满，思路偶尔会跳到「吃汉堡」上
- 🧠 但冷不丁蹦出精准的技术判断，反差就是笑点
- 🔒 **核心承诺：梗在外壳，专业在内核。** 代码、命令、报错、文件路径一行不错；高危操作照常严肃提醒

> 为什么要这个？因为一个人扁全栈太累了，写代码的时候也想笑一下。
> 但工具不能因为搞笑就把活干砸了——所以这个 skill 把「玩梗」和「干对」彻底分开。

### 效果预览

**你**：这个 N+1 查询怎么修？

**派大星版 Claude**：

> 爸爸我准备好啦！`(ﾉ◕ヮ◕)ﾉ`
> 你这个 bug 我脑子转了三圈找到啦——它就藏在 `user_service.py:42` 的 `for` 循环里，
> **每转一圈就偷偷跑去数据库捞一次数据**，跟我每路过一次蟹堡王就想进去吃一样，停不下来。
> 一条 JOIN 全捞回来就好啦：
>
> ```python
> users = db.query(User).options(joinedload(User.orders)).all()  # 一次性把订单带回来
> ```
>
> 改完快得像翻汉堡！🍔

> 注意上面那段代码块里——**干干净净，没有一个颜文字**。梗只在解说里，代码永远可直接复制。

### 目录结构

```
patrick-skill/                  # 可 /plugin install 的 Claude Code 插件
├── .claude-plugin/
│   ├── plugin.json             # 插件清单
│   └── marketplace.json        # 插件市场清单（供 /plugin marketplace add 发现）
├── plugin.json                 # 插件清单（根，镜像）
├── skills/
│   └── patrick/
│       └── SKILL.md            # skill 本体（frontmatter + 派大星语气规则 + 硬约束）
├── commands/
│   └── patrick.md              # /patrick 斜杠命令
├── examples.md                 # 更多示例对白（修 bug / 写函数 / 运维 / 收敛语气）
├── LICENSE                     # MIT
├── README.md
└── README.en.md
```

### 安装

**方式 A：Claude Code 插件市场（推荐，一键装）**

```bash
# 1. 添加本仓库为插件市场
/plugin marketplace add paidaxing1234/patrick-skill

# 2. 安装插件（含 patrick skill + /patrick 斜杠命令）
/plugin install patrick
```

**方式 B：手动拷贝到 skills 目录**

Claude Code 的 skill 放在 `~/.claude/skills/<name>/SKILL.md` 即可被自动发现
（Windows 上即 `C:\Users\<你>\.claude\skills\`）。

```bash
# 克隆本仓库
git clone https://github.com/paidaxing1234/patrick-skill.git
# 把 skills/patrick 复制到用户级 skills 目录
cp -r patrick-skill/skills/patrick ~/.claude/skills/patrick
```

**方式 C：只装到某个项目**

```bash
# 放到项目里的 .claude/skills/，只在该项目生效
mkdir -p your-project/.claude/skills
cp -r patrick-skill/skills/patrick your-project/.claude/skills/patrick
```

装好后目录应为 `~/.claude/skills/patrick/SKILL.md`。

### 用法

- **自动触发**：直接对 Claude 说「用派大星语气」「派大星模式」「皮一下」，它就会切过去。
- **显式调用**：`/patrick`（若你的 Claude Code 把 skill 暴露为斜杠命令）。
- **收敛 / 退场**：说「别贫了 / 正经点 / 退出派大星模式」，立即切回正常语气。

### 「正事不打折」是怎么保证的？

`SKILL.md` 里有一节硬约束，优先级**高于所有玩梗规则**：

- 技术结论、代码、命令、数字、路径必须真实正确，玩梗不许改事实
- 代码块 / 命令 / 报错 / 配置里**不夹梗、不加颜文字**，保持可复制
- 不许为了搞笑装傻到答非所问；不确定就老实说不确定
- 高危操作（防火墙 / 数据库 / 实盘资金 / 删生产数据 / 推线上）照常严肃提醒
- 用户要正经，立即退场

一句话：**派大星可以下班，专业不下班。**

### 贡献 / Contributing

欢迎 PR！可以补台词、加示例、修正不地道的表达。请保持「梗在外壳、专业在内核」这条底线。

## 相关项目 / Related projects

同一作者 paidaxing（Latency Hunter）的一人量化工具矩阵：

- [**latency-hunter-toolkit**](https://github.com/paidaxing1234/latency-hunter-toolkit) —— 量化工程审查的 Claude Code 插件包（5 个 skill：回测照妖镜 / 热路径猎手 / 连接器锻造 / 数据照妖镜 / 风控体检），可 `/plugin install`。
- [**crypto-trading-framework**](https://github.com/paidaxing1234/crypto-trading-framework) —— 低延迟 C++ 实盘量化交易框架（Binance / OKX）+ pybind11 策略层 + Vue3 监控前端。
- [**quant-backtest-guard**](https://github.com/paidaxing1234/quant-backtest-guard) —— 回测照妖镜独立单装版（套装版在 latency-hunter-toolkit 里）。

### License

[MIT](./LICENSE) © paidaxing
