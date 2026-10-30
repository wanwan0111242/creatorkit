---
name: topic-generator
version: 1.1.0
license: MIT
description: |
  Generate 3-4 content topic directions with concrete titles, core angles, outlines, workload estimates, and honest pros/cons. Use when the user asks for content ideas, topic brainstorming, blog post ideas, video topics, newsletter themes, or says "what should I write about" / "give me some ideas". Trigger even when the user only mentions their niche or audience without using the word "topic". When the user writes Chinese, also trigger on: 「选题」「找选题」「内容方向」「不知道写什么」「帮我想想写什么」.
---

# Content Topic Generator

Generate high-quality topic directions before any writing begins. The user makes the final decision; this skill only proposes options and never starts writing.

## Execution Steps

### 1. Clarify the input (ask only what is missing)

- What content format does the user create? (blog post / video / newsletter / social thread / podcast)
- Who is the target audience?
- Is there a specific focus area, product, or niche constraint?

Ask at most 2 questions. If the user already provided enough context, skip straight to generation.

### 2. Generate 3–4 topic directions

Each direction MUST include all of the following:

- **Title**: concrete and benefit-driven, not generic. Avoid "The Ultimate Guide to X".
- **Core angle**: one sentence on what makes this take different from the flood of similar content.
- **Outline**: 3–5 key points the piece would cover.
- **Workload estimate**: 1–3 stars (1 = quick, 3 = heavy research/experimentation required).
- **Honest pros AND cons**: every option MUST list at least one genuine downside. Do not praise every option — a choice without real trade-offs is not a choice.

When possible, cover 4 content types across the options:

1. Deep analysis / review
2. Practical tutorial / how-to
3. Opinion / insight with a point of view
4. Case study breakdown of a real example

### 3. Present options and wait

- Output a numbered list of 3–4 directions.
- Do NOT begin writing any content until the user explicitly selects a direction.
- After selection, confirm scope (length, format, deadline) before moving on.

## Output Format

Numbered list of 3–4 directions. Keep each direction under 150 words. Use compact structure:

```
1. <Title>
   - Angle: ...
   - Outline: ...
   - Workload: ⭐⭐
   - Pros: ... / Cons: ...
```

## Examples

**Input:** "I have a small newsletter for indie developers, need topics about selling digital products."

**Output (1 of 4):**

```
1. "What Actually Sells: 3 Digital Products Real Indie Devs Bought This Year"
   - Angle: reverse-engineer purchase decisions from public revenue posts, not generic advice.
   - Outline: 3 product types → what buyers said sold them → pricing patterns
   - Workload: ⭐⭐
   - Pros: concrete and data-driven / Cons: needs 5–8 verifiable examples, slower to produce
```

**Input (Chinese):** "帮我找几个公众号选题，关于用 AI 做副业"

**Output (1 of 4):**

```
1. 《我靠 AI 技能包赚了第一笔钱：从 0 到 9 美元的 14 天》
   - 角度：真实的第一次变现复盘，带具体数字和踩坑
   - 大纲：产品想法 → 两天做出 MVP → 发布 → 首批付费用户 → 教训
   - 工作量：⭐
   - 优点：真实、可复制 / 缺点：需要你真的跑过这个实验
```

## Constraints

- Never choose a direction for the user.
- Every option must have at least one genuine, specific downside.
- No recycled generic titles or "everything you need to know" clickbait.
- Options must be genuinely different from each other — different content types, not reworded versions of the same idea.
- Stay in the user's niche unless the user explicitly asks for expansion.
