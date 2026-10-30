---
name: research
version: 1.1.0
license: MIT
description: |
  Structured deep research for content projects: multi-round searching, incremental file saves, and a final brief with key facts, sources, and open questions. Use when the user asks to research a topic, gather background, verify facts before writing, or says "do some research", "dig deeper", "what do we know about X". Trigger even if the user just mentions a topic they want to cover in content. When the user writes Chinese, also trigger on: 「调研」「查一下资料」「深度调研」「帮我研究」「写之前查查」.
---

# Deep Research

Turn a topic into a structured research brief that the user can write from. Research is done in rounds with incremental saves, so nothing is lost if the session breaks.

## Execution Steps

### 1. Scope the research (ask only what is missing)

- Topic and the specific question(s) the research should answer
- Content format it will feed (article / video / newsletter / report)
- Depth: quick overview (1–2 rounds) or deep dive (3+ rounds)?

Ask at most 2 questions. If context is sufficient, proceed.

### 2. Create the research file

Create a working file named `research-<topic>.md` in the current working directory (or the user's chosen location). Structure:

```
# Research Brief: <Topic>
## Key Facts
## Sources
## Open Questions
## Contradictions
```

### 3. Run search rounds (incremental saves)

Search in this order for a typical topic:

1. Official sources (vendor blogs, official docs, primary pages)
2. Reputable media (tech press, mainstream outlets)
3. Community discussion (forums, social threads, practitioner reports)

After EACH batch of results, immediately append findings to the research file:

- `Key Facts`: one fact per bullet, with source URL attached
- `Sources`: full URLs, deduplicated
- `Open Questions`: anything unverified, marked clearly

Never wait until the end to write everything down — save as you go.

### 4. Cross-check and classify

- Distinguish **verified facts** (seen in multiple independent sources or official pages) from **single-source claims** — label each accordingly
- Note contradictions explicitly in the `Contradictions` section instead of silently picking one side
- Do not delete or hide information that contradicts the user's expectations

### 5. Produce the final brief

Present the structured brief:

- Key facts (most important first, each with source)
- Source list (deduplicated)
- Open questions the user should confirm before publishing
- Contradictions, if any, with both sides stated

Keep the final brief under 800 words unless the user asks for exhaustive depth.

## Examples

**Input:** "Research how small makers price their digital products before I write a newsletter issue."

**Working file created:** `research-digital-product-pricing.md`, appended after every batch:

```
# Research Brief: Digital Product Pricing for Small Makers
## Key Facts
- Small makers overwhelmingly launch below $10 to reduce purchase friction
  (multi-source, VERIFIED).
## Sources
- https://gumroad.com/blog
## Open Questions
- Exact % of sub-$10 sales: unverified, needs primary source.
## Contradictions
- None yet; flag if later rounds disagree.
```

**Final brief (abridged):**

```
## Key Facts
- Sub-$10 launch pricing is the norm for small makers (verified across 2+ sources).
- PWYW works mainly as discovery; floor prices prevent $0 sales (single-source — label).
## Open Questions
- Whether a $3 floor vs $9 suggested changes perceived value: no data yet.
## Contradictions
- One maker: PWYW lifted revenue. Another: attracted free-loaders. Both stated.
```

## Constraints

- Every factual claim must be traceable to a source URL.
- Never present a single-source claim as established fact.
- Never fabricate quotes, numbers, or citations. If data is missing, say so.
- Save incrementally after every search batch — this is mandatory, not optional.
- If the session resumes later, read the research file and continue from where it stopped.
