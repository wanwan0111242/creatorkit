# Contributing to CreatorKit

Thanks for your interest in improving CreatorKit! This project is a small, open-source skill kit — contributions of any size are welcome.

## Ways to contribute

### 1. Improve a skill

Each skill is a single `SKILL.md` file. If a skill's trigger words miss common phrasings, its steps are ambiguous, or its output format could be better — open an issue first to discuss, then a PR.

**Quality bar for SKILL.md edits:**

- `description` must include trigger phrases (English + Chinese) and state clearly *when* to use the skill.
- Execution steps must be concrete and actionable, not vague ("analyze the content").
- Every skill must have an `Output Format` section and a `Constraints` section.
- Add real input/output examples to the `Examples` section when behavior changes.

### 2. Add examples

Share a real or realistic sample of what a skill produces (see `examples/`). A good example shows input → output and notes what the user had to confirm.

### 3. Fix docs

Typos, broken links, unclear install steps in `README.md` / `README_CN.md` — all welcome.

### 4. Report issues

- Bugs: describe what you expected vs. what happened, plus the tool (Claude Code / Cursor / Codex / Gemini CLI) and version.
- Feature ideas: explain the workflow gap you're trying to fill.

## Development workflow

1. Fork the repository.
2. Create a feature branch: `git checkout -b feat/improve-topic-generator`.
3. Commit with a descriptive message (e.g. `feat: add examples to topic-generator`).
4. Open a Pull Request with a short description and the checklist below.

**PR checklist:**

- [ ] I read the `SKILL.md` structure guidance (frontmatter `name` + `description`, steps, output format, constraints)
- [ ] My changes keep skills standalone — no external dependencies, no code
- [ ] I updated `README.md` / `README_CN.md` if the change affects install or usage
- [ ] I tested the skill's trigger phrases work in at least one tool
- [ ] My examples are realistic and not fabricated facts

## Code of conduct

Be kind and constructive. All contributions are licensed under the MIT License — by contributing you agree to that.
