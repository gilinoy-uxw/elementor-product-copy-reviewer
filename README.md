# 🪶 Elementor Copy Reviewer Skill

An AI‑powered product copy reviewer built for [Elementor](https://elementor.com).  
This skill checks text or screenshots against Elementor’s **brand glossary** and **voice & tone guidelines**, identifies misalignments, explains why, and suggests improved, on‑brand alternatives.

Compatible with **Claude Desktop**, **Cursor**, **Codex (CLI/IDE)**, and **Claude Code**.

---

## ✨ What It Does

The Elementor Copy Reviewer helps writers, designers, and product teams ensure all product copy follows official terminology and voice standards.

It:

- Detects incorrect or inconsistent product terms  
- Checks tone, clarity, and grammar against brand rules  
- Explains *why* text is off‑brand  
- Suggests precise, improved alternatives  
- Outputs structured JSON feedback for easy integration or automation

---

## 🧩 Folder Structure

```
elementor-copy-reviewer/
├── SKILL.md              # Metadata for Claude, Codex, Cursor
├── prompts/
│   └── review.txt        # Main analysis prompt (logic)
├── data/
│   ├── glossary.json     # Approved/avoided terms and notes
│   └── writing_rules.json# Codified brand and tone rules
└── README.md             # You’re here ✅
```

---

## 🧠 How It Works

1. The skill loads the glossary and writing rules as reference.
2. When a user pastes copy or uploads a screenshot:
   - Extracts text (OCR supported in compatible tools)
   - Compares wording and tone to your rules
   - Returns structured feedback:

```json
{
  "issues": [
    {
      "type": "Glossary",
      "term_or_rule": "Editor Pro",
      "issue": "Used 'Elementor pro' — incorrect capitalization and ordering",
      "rationale": "Per glossary, correct form is 'Editor Pro'.",
      "suggestion": "Upgrade to Editor Pro for advanced features."
    }
  ],
  "improved_text": "Upgrade to Editor Pro for advanced features."
}
```

---

## 🚀 Getting Started

### ▶️ 1. Clone or Download

```bash
git clone [github.com](https://github.com/elementor/elementor-copy-reviewer-skill)
```

### 💻 2. Use in Claude Desktop

1. Zip the folder  
2. Upload via **Settings → Skills → Upload skill**

### 🧠 3. Use in Cursor

1. In Cursor, open **Settings → Rules, Skills, Subagents**  
2. Click **New Skill** (it opens a `/create-skill` chat)  
3. Paste this line:

   ```
   Elementor Copy Reviewer skill:
   Analyze any text or screenshot and check it against Elementor’s brand glossary (data/glossary.json) and writing rules (data/writing_rules.json). Identify what’s off, explain why, and suggest improved, on‑brand alternatives.
   ```
4. Then add the `/data` folder with both JSON files.  
5. Save — Cursor will create the local skill automatically.

### ⚙️ 4. Use in Codex (CLI or IDE)

Move or link the folder into your local Codex skill directory:

```bash
~/.codex/skills/elementor-copy-reviewer/
```

Restart Codex, then run your skill:

```bash
/use-skill Elementor Copy Reviewer
```

---

## 💬 Example Prompt

```
Review this copy for Elementor style:
"Upgrade to Elementor pro for the best AI integration!"
```

---

## 🧩 Output Example

```json
{
  "issues": [
    {
      "type": "Glossary",
      "term_or_rule": "Editor Pro",
      "issue": "Used 'Elementor pro' — incorrect capitalization and ordering",
      "rationale": "Per glossary, correct term is 'Editor Pro'.",
      "suggestion": "Upgrade to Editor Pro for advanced features."
    },
    {
      "type": "Tone",
      "term_or_rule": "angie-tone",
      "issue": "Overly promotional phrasing 'best AI integration'.",
      "rationale": "Avoid exaggerated claims. Focus on user value.",
      "suggestion": "Access advanced AI tools for faster workflows."
    }
  ],
  "improved_text": "Upgrade to Editor Pro and access advanced AI tools that speed up your workflow."
}
```

---

## 🛠️ Customization

- **Update `data/glossary.json`** to edit or expand approved product terms.  
- **Update `data/writing_rules.json`** to add new tone, grammar, or clarity rules.  
- **Edit `prompts/review.txt`** to change how results are formatted or summarized.

---

## 🪪 License

Creative Commons Attribution‑NonCommercial 4.0 International  
© Elementor Ltd., 2024

---

## 👩‍💻 Contributors

**Elementor Content Design Team**  
Built with care for creators everywhere.
