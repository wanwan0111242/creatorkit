# CreatorKit —— AI 内容创作技能包

**把 AI 编程助手变成你的内容创作搭档。**

![License: MIT](https://img.shields.io/badge/许可-MIT-green.svg)
![Version](https://img.shields.io/badge/版本-v1.1.0-blue.svg)
![Standard](https://img.shields.io/badge/标准-Agent%20Skills%20(agentskills.io)-orange.svg)

不再每开一个新对话就重复解释你的工作流程。CreatorKit 把内容创作管线——选题构思、深度调研、去 AI 味的审校——打包成三个即装即用的 Agent Skill，兼容 Claude Code、Cursor、Codex、Gemini CLI 以及所有支持开放 [Agent Skills](https://agentskills.io) 标准的工具。

基于 Agent Skills 开放标准：每个技能就是一个纯文本 `SKILL.md` 文件——没有代码、没有依赖、无需配置，把文件夹放进指定目录即可。

## 包含内容

| 技能 | 作用 |
|---|---|
| `topic-generator`（选题生成） | 生成 3-4 个真正有差异的内容方向，含标题、角度、大纲、工作量星级与真实优劣分析。你选定前绝不擅自开写。 |
| `research`（深度调研） | 多轮结构化调研、增量保存到文件、交叉核验来源，产出含关键事实、来源清单与待确认问题的调研简报。 |
| `proofreader`（三遍审校） | 三遍审校：查事实 → 去 AI 味（6 大类 AI 腔识别清单）→ 磨细节。给出具体改写方案，而不是模糊建议。 |

## 项目结构

```
creatorkit/
├── README.md            # 英文说明
├── README_CN.md         # 本文件（中文）
├── LICENSE              # MIT 许可
├── CONTRIBUTING.md      # 贡献指南
├── examples/            # 每个技能的真实输入 → 输出演示
│   ├── topic-generator-example.md
│   ├── research-example.md
│   └── proofreader-example.md
└── skills/
    ├── topic-generator/SKILL.md
    ├── research/SKILL.md
    └── proofreader/SKILL.md
```

## 安装方法

### Claude Code

```bash
mkdir -p ~/.claude/skills
cp -r skills/topic-generator skills/research skills/proofreader ~/.claude/skills/
```

只用于单个项目（项目级安装）：

```bash
mkdir -p .claude/skills
cp -r skills/* .claude/skills/
```

### Cursor

```bash
mkdir -p .cursor/skills
cp -r skills/* .cursor/skills/
```

### OpenAI Codex

```bash
mkdir -p .codex/skills
cp -r skills/* .codex/skills/
```

### Gemini CLI

```bash
mkdir -p .gemini/skills
cp -r skills/* .gemini/skills/
```

### GitHub Copilot

在仓库根目录创建 `.github/skills` 目录（个人级使用 `~/.agents/skills`），把技能文件夹复制进去。

> 其他支持 Agent Skills 标准的工具：把每个 `skill-name/` 文件夹复制到它的 skills 目录即可，路径规律永远是 `.<工具名>/skills/<技能名>/SKILL.md`。

## 使用示例

- *"给我 5 个关于 AI 的 Newsletter 选题"* → `topic-generator` 给出方向，你选一个。
- *"调研一下竞争对手怎么定价"* → `research` 多轮搜索、增量保存、返回带来源的简报。
- *"这稿子太 AI 了，帮我改自然一点"* → `proofreader` 三遍审校，输出编辑报告。

`examples/` 目录里有三个技能的完整输入 → 输出演示。

## 技能如何触发

每个技能的 `description` 里内置了中英文触发词，你可以自然地说"帮我找选题""调研这个方向""润色这篇稿子"即可自动触发；也可以输入斜杠命令强制加载（如 `/topic-generator`）。

## 参与贡献

欢迎提交 bug 报告、技能改进与示例补充，见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 更新日志

- **v1.1.0**（2026-10-30）：新增 MIT LICENSE、CONTRIBUTING.md、`.gitignore`、`examples/` 演示、每个技能的 Examples 区、frontmatter 元信息（版本/许可）、README 项目结构与 FAQ。
- **v1.0.0**（2026-10-30）：首发——3 个技能（选题/调研/审校）、中英双语 README 与触发词。

## 常见问题

**我的工具能用吗？**
只要支持 Agent Skills 标准（agentskills.io）就能用——复制文件夹即可。已在 Claude Code、Cursor、Codex、Gemini CLI、GitHub Copilot 验证。

**需要付费吗？**
不需要。开源（MIT）、免费使用。如果觉得有用想支持开发，采用自主定价（Pay What You Want）：推荐 ¥9，最低 ¥3——你觉得它值得多少，就付多少，每一份支持都是创作者继续迭代的动力。

**可以修改技能吗？**
可以，MIT 许可——自由使用、修改、再发布，打包成自己的技能包也行。

## 免责声明

CreatorKit 是独立的社区项目，**与 Anthropic、OpenAI、Google、Cursor、GitHub 均无隶属、背书或赞助关系**。文中提及的 "Claude Code"、"Cursor"、"Codex"、"Gemini CLI"、"GitHub Copilot" 等产品名称均为其各自所有者的商标，仅用于描述与开放 Agent Skills 标准（agentskills.io）的兼容性，不构成任何官方关联声明。

## 许可

MIT —— 自由使用、修改、再发布。
