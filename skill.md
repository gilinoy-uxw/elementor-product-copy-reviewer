---
name: "Elementor Copy Reviewer"
version: "2.0.0"
description: "Reviews product copy against Elementor's brand glossary, voice & tone guidelines, and surface-area writing standards. Identifies violations, explains rationale, and always suggests a concrete improved version."
author: "Elementor Content Design"
license: "CC-BY-NC-4.0"
entry_point: "prompts/review.txt"
---

# Elementor Copy Reviewer

This skill analyzes product copy — from single strings to full codebases — and checks it against Elementor's brand glossary, writing guidelines, and surface-area tone standards. It identifies issues, explains why they miss the mark, and always suggests a concrete rewrite.

## What it checks

| Dimension | What it catches |
|---|---|
| **Glossary** | Wrong or banned product terms, incorrect capitalization, wrong term for context |
| **Voice** | Copy that doesn't sound like Elementor — inflated, robotic, or removes user agency |
| **Tone** | Wrong tone for the surface type (error vs onboarding vs CTA vs destructive action) |
| **Grammar** | Passive voice, title case, wordiness, empty intensifiers, missing Oxford comma |
| **Clarity** | Vague, ambiguous, or harder to understand than it needs to be |
| **Writing Quality** | Technically correct but a meaningfully better version exists |

## Surface areas

The skill applies different tone standards based on context:
- Error messages: direct, calm, empathic, always with a next step
- Empty states: invitations to act, not absences
- Onboarding: warmer, more character, one step at a time
- Success states: confirm + suggest next step
- CTAs: strong verb, outcome-focused
- Tooltips: "what does this do for me?" not "what is this?"
- Destructive actions: explicit, never casual
- Angie responses: collaborative, transparent, control-preserving
- Navigation labels: parallel, sentence case, scannable
- Upgrade/pricing: benefit-led, never pushy
- Settings: precise, neutral, specific

## Usage

### In Claude Desktop / Cursor

**Single string or screen:**
> "Review this copy for Elementor style: [paste copy]"

**Full component or flow:**
> "Review all user-facing strings in this component for Elementor style."

**Codebase:**
> "Review the user-facing strings in this repository for Elementor style."
> The skill will scan .jsx, .tsx, .js, .ts files, skip translation files, and group output by file path.

### In the Figma plugin

The plugin handles prompt construction automatically. The skill data files (`glossary.json`, `writing-guidelines.json`, `surface-areas.json`) are loaded dynamically from GitHub on each analysis run.

## When it says "no issues"

If the copy is correct and no meaningfully better version exists, the skill says so clearly. It does not force changes. Professional restraint is part of the skill's credibility.

## Data files

| File | Purpose |
|---|---|
| `data/glossary.json` | Approved and banned Elementor product terms with usage notes |
| `data/writing-guidelines.json` | Voice, tone, grammar, and style rules with examples |
| `data/surface-areas.json` | Tone expectations and rules per UI context type |
| `prompts/review.txt` | Main review prompt loaded by the skill runner |

## Scope

- **Component level**: all user-facing strings in one component
- **Screen level**: all strings visible on one screen
- **Flow level**: all strings across a multi-screen flow, plus cross-screen consistency checks (repetition, tone drift, hierarchy, momentum)
- **Codebase level**: repository-wide scan, grouped by file, user-facing strings only
