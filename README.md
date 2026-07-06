# AI 开发四象限模板 🧭

> 基于 Anthropic 工程师 Thariq 的四象限框架，用 4 个 Prompt 模板解决 AI 协作中的"未知"问题。

## 为什么需要这个？

日常开发中，最大的问题不是 AI 不会写代码，而是 **AI 不知道你知道的东西**（未知已知），或者 **你们都没考虑到的问题**（未知未知）。

这个 Skill 提供 4 个可直接复制的 Prompt 模板，覆盖完整的 AI 辅助开发流程。

## 四个模板

| 模板 | 解决象限 | 使用时机 |
|------|---------|---------|
| 👁️ 盲点审查 | 未知未知 | 接手新项目/新模块的第一步 |
| 🎤 反向采访 | 已知未知 | 写代码之前先澄清需求 |
| 📝 动态实施笔记 | 未知已知 | AI 跑长任务时保持透明 |
| ✅ 后置测验 | 未知已知 | 合并代码前的人工审核 |

## 推荐流程

```
需求来了 → 反向采访 → 盲点审查 → 写代码(带实施笔记) → 后置测验 → merge
```

## 安装

### Claude Code（用户级）

```bash
cp SKILL.md ~/.claude/skills/ai-dev-four-templates.md
```

### Claude Code（项目级）

```bash
mkdir -p .claude/skills
cp SKILL.md .claude/skills/ai-dev-four-templates.md
```

### Hermes Agent

将 `SKILL.md` 放入 `~/.hermes/skills/` 目录即可自动加载。

## 核心原则

> **一次廉价对话 > 一次昂贵返工**

## 来源

- Anthropic 工程师 Thariq 的四象限框架
- 南山老实人「顶级 AI 工程师的 Prompt 模板」视频整理

## License

MIT
