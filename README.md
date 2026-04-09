# 🪶 Elementor Copy Reviewer Skill

An AI‑powered product copy reviewer built for [Elementor](https://elementor.com).  
This skill checks text or screenshots against Elementor’s **brand glossary** and **voice & tone guidelines**, identifies misalignments, explains why, and suggests improved, on‑brand alternatives.

Compatible with **Claude Desktop**, **Cursor**, **Codex (CLI/IDE)**, and **Claude Code**.

---

## ✨ What It Does

The Elementor Copy Reviewer helps writers, designers, and product teams ensure every piece of copy follows official terminology and voice standards.

It:

- Detects incorrect or inconsistent product terms  
- Checks tone, clarity, and grammar against brand rules  
- Explains *why* text is off‑brand  
- Suggests precise, improved alternatives  
- Outputs structured JSON feedback for easy integration or automation

---
## 🧠 How It Works
1. The skill loads your glossary and writing rules as reference.
2. When a user pastes copy or uploads a screenshot:
   - Extracts text (visual OCR available in compatible tools)
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

----
**🚀 Getting Started**

1. Clone or download

git clone [github.com](https://github.com/elementor/elementor-copy-reviewer-skill)
2. (Claude Desktop)
Zip the folder and upload it via: Settings → Skills → Upload skill

3. (Cursor)
In the command bar, type:
/create-skill Help me create this skill for Cursor:
Then paste the short description from SKILL.md,
add the /data folder with both JSON files, and save.

4. (Codex CLI)
Move the folder to your local skills directory:

~/.codex/skills/elementor-copy-reviewer/
💬 Example Prompt


Review this copy for Elementor style:
"Upgrade to Elementor pro for the best AI integration!"
🧩 Output
You’ll receive a structured evaluation of:

Word choice & terminology
Tone (courageous, intelligent, visionary)
Grammar & style (sentence case, clarity, conciseness)
Product‑specific tone (Editor, Manage, Angie, etc.)
🛠️ Customization
Update data/glossary.json for term changes.
Extend data/writing_rules.json for new tone or grammar guidance.
Adjust prompts/review.txt if you’d like a different output style (e.g., Markdown summary).
🪪 License
Creative Commons Attribution‑NonCommercial 4.0 International
© Elementor Ltd., 2024

🧑‍💻 Contributors
Elementor Content Design Team
Built with love for creators everywhere.




