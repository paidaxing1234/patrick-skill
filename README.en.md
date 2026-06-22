# 🌟 patrick-skill

[简体中文](./README.md) | **English**

> `patrick-skill` is a [Claude Code](https://claude.com/claude-code) skill that makes Claude work in the voice of Patrick Star (the pink starfish from SpongeBob) — jokes on the outside, professionalism on the inside: the work stays serious, the engineering never compromised.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-8A63D2.svg)](https://claude.com/claude-code)
[![Voice: Patrick Star](https://img.shields.io/badge/voice-%E6%B4%BE%E5%A4%A7%E6%98%9F%20%F0%9F%8C%9F-FF8FB1.svg)](#)

---

### What is this?

`patrick-skill` is a [Claude Code](https://claude.com/claude-code) **Skill**. Once installed,
just tell Claude *"talk like Patrick Star"* (or `/patrick`) and it will pair-program with you in the
voice of the lovable, dim-but-enthusiastic pink starfish from *SpongeBob SquarePants*:

- 🎈 Goofy, hyper-enthusiastic, occasionally distracted by hamburgers
- 🧠 …then drops a precise technical verdict out of nowhere
- 🔒 **Core promise: jokes on the outside, professionalism on the inside.** Code, commands,
  stack traces, and file paths are always correct; dangerous operations still get serious warnings.

### Why?

Building a whole stack solo is exhausting. Coding should be allowed to be fun. But a dev tool must
never trade correctness for comedy — so this skill keeps **"being funny"** and **"being right"**
strictly separated.

### Install

**Option A — Claude Code plugin marketplace (recommended, one-liner):**

```bash
/plugin marketplace add paidaxing1234/patrick-skill
/plugin install patrick
```

**Option B — manual copy.** Claude Code auto-discovers skills at `~/.claude/skills/<name>/SKILL.md`
(`C:\Users\<you>\.claude\skills\` on Windows).

```bash
git clone https://github.com/paidaxing1234/patrick-skill.git
cp -r patrick-skill/skills/patrick ~/.claude/skills/patrick
```

For a single project, copy into that project's `.claude/skills/` instead.

### Usage

- **Auto**: say *"use the Patrick voice"* / *"Patrick mode"*.
- **Explicit**: `/patrick`.
- **Dial it back**: say *"be serious"* / *"exit Patrick mode"* and Claude returns to its normal voice.

### The "never compromise the work" guardrail

`SKILL.md` contains a hard-constraints section that **overrides all the joke rules**: facts, code,
commands, numbers, and paths must be correct; code blocks stay meme-free and copy-pastable; no
playing dumb to dodge a real answer; dangerous ops always get a serious warning.

> Patrick can clock out. Professionalism never does.

## Related projects

The solo-quant tooling matrix by the same author, paidaxing (Latency Hunter):

- [**latency-hunter-toolkit**](https://github.com/paidaxing1234/latency-hunter-toolkit) — a Claude Code plugin pack for quant-engineering review (5 skills: backtest audit / hot-path hunter / connector forge / data sanity / risk checkup), installable via `/plugin install`.
- [**crypto-trading-framework**](https://github.com/paidaxing1234/crypto-trading-framework) — a low-latency C++ live trading framework (Binance / OKX) with a pybind11 strategy layer and a Vue3 monitoring frontend.
- [**quant-backtest-guard**](https://github.com/paidaxing1234/quant-backtest-guard) — the standalone single-install edition of the backtest audit skill (the bundled edition lives inside latency-hunter-toolkit).

### License

[MIT](./LICENSE) © paidaxing
