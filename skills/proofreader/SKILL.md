---
name: proofreader
version: 1.1.0
license: MIT
description: |
  Three-pass editing for AI-assisted writing: fact check, de-AI-ify style, and fine-tune details, with a 6-category AI-flavor detection checklist and concrete rewrites. Use when the user asks to proofread, polish, review a draft, make text sound less robotic, reduce AI detection, or says "this sounds AI-written", "make it more natural", "check this article". Trigger even when the user says "look at this" right after finishing a draft. When the user writes Chinese, also trigger on: 「审校」「润色」「改一改」「太AI了」「AI味太重」「帮我看下这篇」「自然一点」.
---

# Three-Pass Proofreader

Edit drafts so they read like a real person wrote them. The goal is to cut AI-flavor and bring AI-detection likelihood down while preserving the user's facts and intent. This skill proposes edits; it never rewrites wholesale or changes meaning without asking.

## Execution Steps

### Pass 1 — Content check (is it RIGHT?)

- Verify facts: numbers, product names, dates, quotes
- Check logic: do claims follow from evidence? Any contradictions?
- Check completeness: is anything promised in the intro missing later?

Fix or flag factual errors first — no amount of style polish matters if the content is wrong. Ask before changing any factual claim.

### Pass 2 — Style check (does it sound HUMAN?)

Work through the 6-category AI-flavor checklist below. For every flagged phrase, propose a concrete rewrite (not just "this sounds stiff").

**1. Filler phrases (套话)**
Remove: "it's important to note that", "in today's fast-paced world", "it is worth mentioning", "all in all", "in conclusion", "needless to say", "delve into", "leverage", "unlock".
Example rewrite: "In today's digital era, leveraging AI tools can unlock significant productivity gains." → "I started using these tools three weeks ago and cut a 3-day task to a day and a half."

**2. AI sentence patterns**
Watch for: "Not only... but also", "Whether... or", "It is X that Y", excessive parallelism, three-item list syndrome ("efficiency, accuracy, and reliability").
Rewrite by varying sentence length and structure.

**3. Over-formal vocabulary**
Replace: "utilize" → "use", "commence" → "start", "subsequently" → "then", "endeavor" → "try", "regarding" → "about".
Add contractions ("don't", "it's", "we'll") where natural.

**4. Mechanical structure**
Flag paragraphs that all follow the same template (topic sentence + example + summary). Vary paragraph openings, add transitions that sound like thinking.

**5. Neutral tone with no point of view**
AI drafts rarely take a side. Add concrete personal reactions, a specific time, a real example, an actual number. "This tool is very powerful" → "The first time I ran it, it refactored my mess of test cases too — that's when I stopped calling it autocomplete."

**6. Missing concrete detail**
Every abstract claim needs a specific anchor: a date, a person, a number, a place, a failure. If a sentence could apply to any tool/person/topic, it needs more specificity.

### Pass 3 — Detail polish (is it PLEASANT to read?)

- Sentence length: flag sentences over 30 words
- Paragraph length: flag paragraphs longer than 3–5 lines on mobile screens
- Punctuation rhythm: excessive dashes, comma splices, or exclamation marks
- Bold frequency: over-bolding loses impact — keep only key terms

## Output Format

Return an edit report, not a full rewrite:

1. **Summary**: 1–2 lines on the draft's main issues
2. **Edits**: numbered list — original (short quote) → revised version → reason (which checklist category)
3. **Residual risks**: anything still unverified or that the user should double-check

Apply direct edits to the file ONLY when the user confirms the report first.

## Examples

**Input:** "In today's fast-paced digital era, leveraging AI tools can unlock significant productivity gains. It is important to note that content creators who utilize these tools may experience improved efficiency, accuracy, and reliability in their workflows."

**Edit report (abridged):**

```
Summary: 100% AI-flavor — filler openers, three-item syndrome, no concrete detail.

Edits:
1. "In today's fast-paced digital era, leveraging AI tools can unlock significant
   productivity gains."
   → "Three weeks ago I let Claude write my first newsletter draft. It took four
      minutes instead of four hours."
   → Reason: filler phrase + over-formal vocab + no concrete anchor (cat 1/3/6)
2. "…content creators who utilize these tools may experience improved efficiency,
   accuracy, and reliability…"
   → "I stopped re-explaining my workflow every session — the skills I installed
      remember it for me."
   → Reason: filler (cat 1), "utilize"→"use" (cat 3), three-item list (cat 2)

Residual risks: rewrites add new claims ("three weeks ago") — confirm before publishing.
```

**Input (Chinese):** "这篇稿子太 AI 了，帮我改自然一点"（接一段 AI 味正文）

**Output:** 同样的编辑报告结构——逐条 原文 → 改写 → 原因（套话 / AI句式 / 过度正式 / 机械结构 / 无观点 / 缺细节），外加残余风险提示。

## Constraints

- Never change facts, names, numbers, or the user's opinions without asking.
- Flag, don't dictate: final style decisions belong to the user.
- Every flagged issue must come with a concrete rewrite, not a vague suggestion.
- Do not strip the user's authentic voice to make text "more standard".
- If the draft is already human-sounding, say so — do not invent edits just to produce output.
