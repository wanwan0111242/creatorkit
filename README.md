# CreatorKit

**3 agent skills that turn your AI coding assistant into a content production partner.**

Stop re-explaining your workflow every session. CreatorKit packages the content-creation pipeline — topic ideation, deep research, and human-sounding editing — into portable skills that work across Claude Code, Cursor, Codex, Gemini CLI, and other tools that support the open [Agent Skills](https://agentskills.io) standard.

Built on the Agent Skills open standard: each skill is a plain `SKILL.md` file — no code, no dependencies, no setup beyond dropping a folder into place.

## What's inside

| Skill | What it does |
|---|---|
| `topic-generator` | Produces 3–4 genuinely different content directions with titles, angles, outlines, workload estimates, and honest pros/cons. Never writes before you choose. |
| `research` | Runs structured multi-round research with incremental file saves, cross-checks claims, and delivers a brief with key facts, sources, and open questions. |
| `proofreader` | Three-pass editing: fact check → de-AI-ify style (6-category AI-flavor checklist) → detail polish. Proposes concrete rewrites instead of vague suggestions. |

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

## How skills trigger

Each skill's `description` includes trigger phrases, so you can also just speak naturally ("what should I write about", "dig into this topic", "polish this"). Or force-load one explicitly with a slash command (e.g. `/topic-generator`).

## License

MIT — use them, remix them, ship your own kit.
