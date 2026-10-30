# CreatorKit

**3 agent skills that turn your AI coding assistant into a content production partner.**

![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)
![Version](https://img.shields.io/badge/version-v1.1.0-blue.svg)
![Standard](https://img.shields.io/badge/standard-Agent%20Skills%20(agentskills.io)-orange.svg)

Stop re-explaining your workflow every session. CreatorKit packages the content-creation pipeline — topic ideation, deep research, and human-sounding editing — into portable skills that work across Claude Code, Cursor, Codex, Gemini CLI, and other tools that support the open [Agent Skills](https://agentskills.io) standard.

Built on the Agent Skills open standard: each skill is a plain `SKILL.md` file — no code, no dependencies, no setup beyond dropping a folder into place.

## What's inside

| Skill | What it does |
|---|---|
| `topic-generator` | Produces 3–4 genuinely different content directions with titles, angles, outlines, workload estimates, and honest pros/cons. Never writes before you choose. |
| `research` | Runs structured multi-round research with incremental file saves, cross-checks claims, and delivers a brief with key facts, sources, and open questions. |
| `proofreader` | Three-pass editing: fact check → de-AI-ify style (6-category AI-flavor checklist) → detail polish. Proposes concrete rewrites instead of vague suggestions. |

## Project structure

```
creatorkit/
├── README.md            # This file (English)
├── README_CN.md         # 中文说明
├── LICENSE              # MIT
├── CONTRIBUTING.md      # Contribution guide
├── examples/            # Realistic input → output demos for each skill
│   ├── topic-generator-example.md
│   ├── research-example.md
│   └── proofreader-example.md
└── skills/
    ├── topic-generator/SKILL.md
    ├── research/SKILL.md
    └── proofreader/SKILL.md
```

## Install

### Claude Code

```bash
mkdir -p ~/.claude/skills
cp -r skills/topic-generator skills/research skills/proofreader ~/.claude/skills/
```

Project-level (only for one project):

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

Create the `.github/skills` directory in your repository (or `~/.agents/skills` for personal skills) and copy the skill folders there.

> Any other tool supporting the Agent Skills standard: copy each `skill-name/` folder into its skills directory. The pattern is always `.<tool>/skills/<skill-name>/SKILL.md`.

## Usage examples

- *"Give me 5 newsletter topics about AI for indie hackers"* → `topic-generator` proposes directions, you pick one.
- *"Research how Gumroad competitors price their digital products"* → `research` runs rounds, saves incrementally, returns a sourced brief.
- *"This draft sounds AI-written, make it more natural"* → `proofreader` runs three passes and hands you an edit report.

See `examples/` for realistic input → output demos of all three skills.

## How skills trigger

Each skill's `description` includes trigger phrases (English + Chinese), so you can also just speak naturally ("what should I write about", "dig into this topic", "polish this"). Or force-load one explicitly with a slash command (e.g. `/topic-generator`).

## Contributing

Bug reports, skill improvements, and example additions are all welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

## Changelog

- **v1.1.0** (2026-10-30): added MIT LICENSE, CONTRIBUTING.md, `.gitignore`, `examples/` demos, `Examples` section in every skill, metadata (version/license) in skill frontmatter, project structure + FAQ in README.
- **v1.0.0** (2026-10-30): initial release — 3 skills (topic-generator, research, proofreader), bilingual README + trigger words.

## FAQ

**Does this work with my tool?**
If your tool supports the Agent Skills standard (agentskills.io), yes — copy the folders, done. Confirmed on Claude Code, Cursor, Codex, Gemini CLI, GitHub Copilot.

**Do I need to pay?**
No. It's open source (MIT) and free to use. If you find it useful and want to support development, [pay what you want](README_CN.md#定价) — $9 suggested / $3 minimum (¥9 / ¥3 in China). Every contribution helps keep it maintained.

**Can I modify the skills?**
Yes — MIT license. Remix them, ship your own kit.

## Disclaimer

CreatorKit is an independent, community-driven project. It is **not affiliated with, endorsed by, or sponsored by** Anthropic, OpenAI, Google, Cursor, or GitHub. Product names such as "Claude Code", "Cursor", "Codex", "Gemini CLI", and "GitHub Copilot" are trademarks of their respective owners; they are mentioned only to describe compatibility with the open Agent Skills standard (agentskills.io).

## License

MIT — use them, remix them, ship your own kit.
