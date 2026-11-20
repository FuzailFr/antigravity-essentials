# Antigravity Essentials

Curated developer bundle designed for **Google Antigravity, Cursor, Claude Code, Windsurf, GitHub Copilot, ChatGPT, Claude.ai, and Gemini**. Focuses on extreme token efficiency (Caveman Lite), pragmatic full-stack engineering, anti-slop code hygiene, and natural language editing.

Works across both free and paid tiers, in web browsers, IDEs, and terminal CLIs.

---

## ⚡ 1-Prompt Universal Quick Install

Copy and paste this single instruction into **any AI agent, CLI, or IDE** (Antigravity, Cursor, Claude Code, Cline, Windsurf, etc.):

```text
Set up the developer rules and skills from https://github.com/FuzailFr/antigravity-essentials.git for this current environment:
1. If in Antigravity: clone this repository to the global plugins directory (~/.gemini/config/plugins/antigravity-essentials).
2. If in Cursor, Claude Code, Windsurf, or Copilot: fetch the matching rule file from the 'templates/' directory (.cursorrules, CLAUDE.md, .windsurfrules, or .github/copilot-instructions.md) and place it at the project root.
3. If in a general coding agent or workspace: load the instructions from 'templates/universal-system-prompt.md' into your active system prompt.
Verify that the configuration is active and summarize the loaded skills.
```

---

## 🌐 Web Browser Setup (ChatGPT, Claude.ai, Gemini Web)

For browser-based chats on free or paid accounts:

1. Open [templates/universal-system-prompt.md](templates/universal-system-prompt.md).
2. Copy the text block inside.
3. Paste it directly into:
   - **ChatGPT:** *Settings* → *Custom Instructions* (or Custom GPT instructions).
   - **Claude.ai:** *Projects* → *Project Instructions* (or paste at the beginning of a conversation).
   - **Gemini:** *Gemini Gems* → *Custom Instructions*.

---

## 💻 Manual Setup

### Google Antigravity
Linux / macOS:
```bash
git clone https://github.com/FuzailFr/antigravity-essentials.git "$HOME/.gemini/config/plugins/antigravity-essentials"
```

Windows (PowerShell):
```powershell
git clone https://github.com/FuzailFr/antigravity-essentials.git "$env:USERPROFILE\.gemini\config\plugins\antigravity-essentials"
```

### Cursor, Claude Code & Windsurf (One-Liners)
Drop rule files directly into any existing repository:

```bash
# Cursor
curl -fsSL https://raw.githubusercontent.com/FuzailFr/antigravity-essentials/main/templates/.cursorrules -o .cursorrules

# Claude Code
curl -fsSL https://raw.githubusercontent.com/FuzailFr/antigravity-essentials/main/templates/CLAUDE.md -o CLAUDE.md

# Windsurf
curl -fsSL https://raw.githubusercontent.com/FuzailFr/antigravity-essentials/main/templates/.windsurfrules -o .windsurfrules
```

---

## 📦 Included Skills & Modules

- **jagoan**: Full-stack engineering, token compression (Caveman Lite), adaptive reasoning (Simple, Efficiency, Deep), and zero-tool assumption.  
  Author: [FuzailFr](https://github.com/FuzailFr)
- **humanizer-indonesia**: Indonesian text editing to remove AI translation artifacts (*kalke*), clichés, and preserve author voice.  
  Author: [Adhi Pribadi](https://github.com/adhiprib/humanizer-indonesia)
- **anti-slop**: Comprehensive rule set covering code comment hygiene, accessible human UI, responsive mobile layouts, and natural copy.  
  Author: [Miqdad Badjuber](https://github.com/miqdadbadjuber/anti-slop)

---

## 📁 Repository Structure

```text
antigravity-essentials/
├── README.md
├── LICENSE
├── templates/
│   ├── .cursorrules               # For Cursor IDE
│   ├── CLAUDE.md                  # For Claude Code CLI
│   ├── .windsurfrules             # For Windsurf IDE
│   ├── copilot-instructions.md    # For GitHub Copilot
│   └── universal-system-prompt.md # For ChatGPT, Claude.ai, Gemini Web
└── skills/
    ├── antislop/
    ├── antislop-code/
    ├── antislop-copywriting/
    ├── antislop-human/
    ├── antislop-layoutmobile/
    ├── antislop-ui/
    ├── humanizer-indonesia/
    └── jagoan/
```

---

## 📄 License

Distributed under the [MIT License](LICENSE). Individual skill modules remain under the copyright and license of their respective authors.
