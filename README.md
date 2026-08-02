<div align="center">

# 🧭 AI 开发四象限模板

### 用 4 个 Prompt 模板，解决 AI 协作中的「未知」问题

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Stars](https://img.shields.io/github/stars/Delight0628/ai-dev-four-templates?style=flat&logo=github)](https://github.com/Delight0628/ai-dev-four-templates/stargazers)
[![Forks](https://img.shields.io/github/forks/Delight0628/ai-dev-four-templates?style=flat&logo=github)](https://github.com/Delight0628/ai-dev-four-templates/network/members)
[![Issues](https://img.shields.io/github/issues/Delight0628/ai-dev-four-templates?style=flat&logo=github)](https://github.com/Delight0628/ai-dev-four-templates/issues)

---

**🛠️ AI 开发四件套模板：Claude Code / Cursor / Codex / Aider 项目初始化模板，开箱即用的 Agent 上下文配置**

> 💡 基于 Anthropic 工程师 Thariq 的四象限框架，覆盖**盲点审查 → 反向采访 → 动态实施笔记 → 后置测验**的完整 AI 辅助开发流程。

<br/>

[快速开始](#-快速开始) · [四个模板](#-四个模板) · [开发流程](#-推荐的日常开发流程) · [贡献指南](#-贡献指南)

</div>

---

## 🎯 为什么需要这个？

日常开发中，最大的问题不是 AI 不会写代码，而是 **AI 不知道你知道的东西**（未知已知），或者 **你们都没考虑到的问题**（未知未知）。

<div align="center">

| 😰 你的痛点 | ✅ 模板的解法 |
|:---:|:---:|
| 接手陌生代码，不知道哪里有坑 | 👁️ 盲点审查 — 扫除未知未知 |
| 需求模糊，写着写着发现方向不对 | 🎤 反向采访 — 澄清已知未知 |
| AI 跑长任务，改了啥完全看不出来 | 📝 动态实施笔记 — 变更透明可见 |
| 代码写完不敢 merge，怕有遗漏 | ✅ 后置测验 — 通过才合并 |

</div>

> 🧠 **核心理念：别急着让 AI 写代码，先花 5 分钟把「未知」扫清楚。**

---

## 📐 理论基础：四象限框架

Anthropic 工程师 Thariq 按「认知 × 表达」维度，把任务中的「未知」分成四类：

<div align="center">

| 象限 | 风险 | 含义 |
|:---:|:---:|:---|
| 已知已知 | 🟢 低 | 你写进 Prompt 的需求，AI 能直接执行 |
| 已知未知 | 🟡 中 | 你知道要探索，但具体实现还没想清楚 |
| **未知已知** | 🔴 **极高** | 你觉得理所当然但 AI 根本不知道 |
| 未知未知 | 🟠 高 | 双方都没考虑到的盲点 |

</div>

---

## 🧩 四个模板

### 👁️ 模板 1：盲点审查

<details>
<summary><b>解决象限</b>：未知未知 · <b>点击展开详情</b></summary>

**什么时候用**：接手新项目/新模块、改不熟悉的代码、开新功能但对现有架构不了解

**Prompt：**

```
我准备在这个代码库加个新功能，但我对这里的[具体模块]一无所知。
请帮我做一次盲点审查，找出我可能忽略的未知未知。
再告诉我接下来该怎么更好地向你提问。
```

**实际效果：**
- 📍 这里有个你可能没注意到的依赖关系
- 📍 改这个模块要注意那个隐藏的约束
- 📍 你接下来应该问这些问题

**典型场景：**
- 🚀 接到需求要改某个服务，先用这个扫雷
- 🆕 新入职接手项目，第一个 Prompt 就用这个
- 🔍 代码审查前先跑一遍，避免遗漏

</details>

---

### 🎤 模板 2：反向采访

<details>
<summary><b>解决象限</b>：已知未知 · <b>点击展开详情</b></summary>

**什么时候用**：产品经理给了需求但细节模糊、自己有想法但还没完全想清楚

**Prompt：**

```
请一次只问我一个问题，揪出我整个想法里所有含糊不清的地方。
优先问那种一旦我的回答变了，就会直接影响你底层架构的关键问题。
```

**实际效果：**

| AI 可能问的问题 | 为什么重要 |
|:---|:---|
| 数据要支持软删除还是硬删除？ | 影响数据库设计和查询逻辑 |
| 需要支持第三方登录吗？ | 影响认证模块架构 |
| 这个接口的 QPS 预期是多少？ | 决定是否需要缓存层 |
| 失败时的回滚策略是什么？ | 影响事务设计 |

> ⚡ **问完之后再让 AI 写代码**，写出来的代码才真正对路。

</details>

---

### 📝 模板 3：动态实施笔记

<details>
<summary><b>解决象限</b>：未知已知 · <b>点击展开详情</b></summary>

**什么时候用**：让 AI 重构大模块、写一堆测试、做跨多个文件的改动

**Prompt：**

```
执行时同步维护 implementation-notes.md，
撞上边缘 case 就记偏离说明再继续。
```

**实际效果：**

AI 一边干活一边记录：

```markdown
## 偏离说明

原计划用 A 方案，但发现 X 文件有历史兼容性问题，
改用 B 方案。影响范围：3个文件，2个接口签名。

## 决策记录

- [2024-XX] 选择方案B而非A，原因：向后兼容
- [2024-XX] 新增缓存层，原因：QPS预期>1000
```

> 🎯 AI 做了 10 个改动你不可能一个个看 diff，有了这个笔记你只看**「偏离说明」**就行。

</details>

---

### ✅ 模板 4：后置测验

<details>
<summary><b>解决象限</b>：未知已知 · <b>点击展开详情</b></summary>

**什么时候用**：AI 帮你改完代码，你要合到主分支之前

**Prompt：**

```
出一份变更报告+测验，我全对通过才准 merge。
```

**实际效果：**

AI 生成一份报告：

1. **📋 变更概览** — 改了哪些文件，每个文件改了什么
2. **💡 逻辑解释** — 为什么要这么改
3. **❓ 测验题**（5-10道）：

   - 这个改动会影响哪个接口的响应格式？
   - 如果用户同时发起两个请求，会不会有竞态问题？
   - 新代码的错误处理和原来一致吗？
   - 回滚时需要做什么？
   - 测试覆盖了哪些边界条件？

> 🛡️ **你必须全答对才能 merge。** 这强制你真正理解每行改动，不是走形式。

</details>

---

## 🚀 快速开始

### 📦 安装方式

#### Claude Code（用户级）

```bash
cp SKILL.md ~/.claude/skills/ai-dev-four-templates.md
```

#### Claude Code（项目级）

```bash
mkdir -p .claude/skills
cp SKILL.md .claude/skills/ai-dev-four-templates.md
```

#### Hermes Agent

将 `SKILL.md` 放入 `~/.hermes/skills/` 目录即可自动加载。

---

## 📋 推荐的日常开发流程

```
需求来了
  ↓
Step 1: 🎤 反向采访（澄清需求细节）
  ↓
Step 2: 👁️ 盲点审查（扫代码库盲区）
  ↓
Step 3: 📝 写代码（带动态实施笔记）
  ↓
Step 4: ✅ 后置测验（通过才 merge）
```

### 场景速查

| 场景 | 用哪些模板 |
|:---|:---|
| 🐛 小改动 / bugfix | 直接写，不用模板 |
| ✨ 新功能开发 | Step 2 → 3 → 4 |
| 🔮 接手陌生项目 | Step 1 → 2 → 3 → 4 |
| ❓ 需求模糊 | Step 2 最重要 |

---

## 💡 核心原则

<div align="center">

### 🏆 一次廉价对话 > 一次昂贵返工

</div>

你让 AI 写了一小时代码，最后发现方向不对要重来——这才是真的浪费。前两步可能你觉得「浪费时间」，但它们能帮你避免 **80% 的返工**。

---

## 🤝 贡献指南

欢迎贡献！你可以：

- 🐛 **提交 Bug** — [Issues](https://github.com/Delight0628/ai-dev-four-templates/issues)
- 💡 **提出新模板** — 发起 Issue 或 PR
- 📝 **完善文档** — 改进说明、添加示例
- ⭐ **Star 本项目** — 帮助更多人发现这个工具

### 如何贡献

1. Fork 本仓库
2. 创建你的特性分支 (`git checkout -b feature/amazing-template`)
3. 提交你的修改 (`git commit -m 'Add amazing template'`)
4. 推送到分支 (`git push origin feature/amazing-template`)
5. 创建一个 Pull Request

---

## 📚 来源

- Anthropic 工程师 Thariq 的四象限框架
- 南山老实人「顶级 AI 工程师的 Prompt 模板」视频整理

---

## 📄 License

[MIT](LICENSE) © 2026 高兴

---

<div align="center">

**如果这个项目对你有帮助，请给个 ⭐ Star 支持一下！**

Made with ❤️ by [Delight0628](https://github.com/Delight0628)

</div>
