# Example: proofreader

Realistic demo of the skill's edit report. Shows original → revised → reason for each flagged item.

## Input (user pastes a draft)

> "In today's fast-paced digital era, leveraging AI tools can unlock significant productivity gains. It is important to note that content creators who utilize these tools may experience improved efficiency, accuracy, and reliability in their workflows. Not only do these tools save time, but they also enhance the quality of the output."

## Edit report (abridged)

**Summary:** Draft is 100% AI-flavor — filler openers, three-item syndrome, no concrete detail. Needs grounding in specifics.

**Edits:**

1. *"In today's fast-paced digital era, leveraging AI tools can unlock significant productivity gains."*
   → **"Three weeks ago I let Claude write my first newsletter draft. It took four minutes instead of four hours."**
   → Reason: filler phrase (category 1) + over-formal vocab (category 3) + no concrete anchor (category 6).

2. *"It is important to note that content creators who utilize these tools may experience improved efficiency, accuracy, and reliability in their workflows."*
   → **"I stopped re-explaining my workflow every session — the skills I installed remember it for me."**
   → Reason: filler (cat 1), "utilize"→"use" (cat 3), three-item list "efficiency, accuracy, and reliability" (cat 2).

3. *"Not only do these tools save time, but they also enhance the quality of the output."*
   → **"The proofread pass caught two factual slips I'd have published."**
   → Reason: "Not only... but also" pattern (cat 2) + vague "quality of the output" (cat 6).

**Residual risks:**

- The rewrite introduces specific claims ("three weeks ago", "two factual slips") — user must confirm these are true before publishing.

## Notes

- The skill flags and proposes; it does not apply edits to the file until the user confirms.
- If a draft is already human-sounding, the skill says so instead of inventing edits.
