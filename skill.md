---
name: "Elementor Copy Reviewer"
version: "1.0.0"
description: "Reviews product copy against Elementor's glossary and brand voice guidelines to ensure clarity, consistency, and tone alignment."
author: "Elementor Content Design"
license: "CC-BY-NC-4.0"
entry_point: "prompts/review.txt"
---

# Elementor Copy Reviewer

This skill analyzes text or screenshots and checks them against Elementor’s brand glossary and writing rules.  
It identifies non‑aligned phrases, explains why they miss the mark, and suggests improved, on‑brand alternatives.

**Features**
- Checks all copy against approved terminology
- Enforces tone, grammar, and voice standards
- Suggests improved versions of text
- Works with Claude Desktop, Codex, Cursor, and compatible tools

**Usage**
1. Upload or paste text in Claude.
2. Run the skill: “Review this copy for Elementor style.”
3. Receive detailed issues JSON + refined text.

Data used:
- `data/glossary.json`
- `data/writing_rules.json`
