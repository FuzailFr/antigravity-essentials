# Antigravity Essentials

Universal developer rules and skill bundle for **Antigravity, Cursor, Claude Code, Windsurf, Copilot, ChatGPT, Claude.ai, and Gemini**. Focuses on token efficiency (Caveman Lite), pragmatic senior engineering, clean comment hygiene, bespoke UI/UX craft, and natural language editing.

Compatible with free and paid tiers across web browsers, IDEs, and terminal CLIs.

---

## Quick Install (Single Prompt)

Paste this instruction into **any AI agent, CLI, or IDE** (Antigravity, Cursor, Claude Code, Cline, Windsurf, etc.):

```text
Set up the developer rules and skills from https://github.com/FuzailFr/antigravity-essentials.git for this current environment:
1. If in Antigravity: clone this repository to the global plugins directory (~/.gemini/config/plugins/antigravity-essentials).
2. If in Cursor, Claude Code, Windsurf, or Copilot: fetch the matching rule file from the 'templates/' directory (.cursorrules, CLAUDE.md, .windsurfrules, or copilot-instructions.md) and place it at the project root.
3. If in a general coding agent or workspace: load the instructions from 'templates/universal-system-prompt.md' into your active system prompt.
Verify that the configuration is active and summarize the loaded skills.
```

---

## Platform Support

| Environment | Supported Tools | Installation Method |
| :--- | :--- | :--- |
| **Agentic IDE** | Antigravity | Run quick install prompt or git clone to plugins directory |
| **Code Editors** | Cursor, Windsurf, Copilot | Copy corresponding file from `templates/` to project root |
| **Terminal CLI** | Claude Code, Aider, Gemini CLI | Use `templates/CLAUDE.md` or set as system prompt |
| **Web Browsers** | ChatGPT, Claude.ai, Gemini (Free/Paid) | Paste `templates/universal-system-prompt.md` into Custom Instructions |

---

## Web Browser Setup (ChatGPT, Claude.ai, Gemini)

1. Open [`templates/universal-system-prompt.md`](templates/universal-system-prompt.md).
2. Copy the text block.
3. Paste into your platform's custom instruction field:
   - **ChatGPT:** *Settings* > *Custom Instructions* (or Custom GPTs).
   - **Claude.ai:** *Projects* > *Project Instructions* (or start of a new chat).
   - **Gemini:** *Gemini Gems* > *Instructions*.

---

## Manual Installation (Terminal)

### Google Antigravity
- Linux / macOS:
  ```bash
  git clone https://github.com/FuzailFr/antigravity-essentials.git "$HOME/.gemini/config/plugins/antigravity-essentials"
  ```
- Windows (PowerShell):
  ```powershell
  git clone https://github.com/FuzailFr/antigravity-essentials.git "$env:USERPROFILE\.gemini\config\plugins\antigravity-essentials"
  ```

### Direct Download for IDEs & CLIs
Download pre-configured rule files directly into your project root:

```bash
# Cursor
curl -fsSL https://raw.githubusercontent.com/FuzailFr/antigravity-essentials/main/templates/.cursorrules -o .cursorrules

# Claude Code
curl -fsSL https://raw.githubusercontent.com/FuzailFr/antigravity-essentials/main/templates/CLAUDE.md -o CLAUDE.md

# Windsurf
curl -fsSL https://raw.githubusercontent.com/FuzailFr/antigravity-essentials/main/templates/.windsurfrules -o .windsurfrules
```

---

## Included Skills & Rules

- **jagoan**  
  Full-stack engineering, token compression (Caveman Lite), adaptive reasoning (Simple, Efficiency, Deep), and zero-tool assumption for constrained web environments.  
  *Author:* [FuzailFr](https://github.com/FuzailFr)

- **ponytail suite** (`ponytail`, `ponytail-review`, `ponytail-audit`, `ponytail-debt`, `ponytail-gain`, `ponytail-help`)  
  Lazy senior dev mode. Forces the smallest change that fully solves the task: YAGNI, standard library first, zero bloat, and surgical code quality reviews.  
  *Author:* [Dietrich Gebert](https://github.com/DietrichGebert/ponytail)

- **anti-slop suite** (`antislop`, `antislop-code`, `antislop-ui`, `antislop-human`, `antislop-layoutmobile`, `antislop-copywriting`)  
  Rule sets enforcing code comment hygiene (no obvious comment filler), accessible human UI, responsive mobile layouts, and natural copy.  
  *Author:* [Miqdad Badjuber](https://github.com/miqdadbadjuber/anti-slop)

- **impeccable**  
  Design language and UX review standard. Polishes visual hierarchy, typography, design tokens, color contrast, and eliminates generic AI aesthetics.  
  *Author:* [Paul Bakaus](https://github.com/pbakaus/impeccable)

- **scroll-craft**  
  Builds premium scroll-driven landing pages with layered heroes, dimensional visual planes, restrained motion, and bespoke mobile composition.  
  *Author:* [Nate Herk](https://github.com/nateherkai/scroll-craft)

- **humanizer-indonesia**  
  Indonesian prose and technical writing editor. Removes translation artifacts (*kalke*), robotic AI syntax, and preserves natural author voice.  
  *Author:* [Adhi Pribadi](https://github.com/adhiprib/humanizer-indonesia)

---

## Repository Structure

```text
antigravity-essentials/
├── README.md
├── LICENSE
├── plugin.json                # Native Antigravity plugin manifest
├── templates/
│   ├── .cursorrules           # For Cursor IDE
│   ├── CLAUDE.md              # For Claude Code CLI
│   ├── .windsurfrules         # For Windsurf IDE
│   ├── copilot-instructions.md# For GitHub Copilot
│   └── universal-system-prompt.md # For ChatGPT, Claude.ai, Gemini Web
└── skills/
    ├── antislop/
    ├── antislop-code/
    ├── antislop-copywriting/
    ├── antislop-human/
    ├── antislop-layoutmobile/
    ├── antislop-ui/
    ├── humanizer-indonesia/
    ├── impeccable/
    ├── jagoan/
    ├── ponytail/
    ├── ponytail-audit/
    ├── ponytail-debt/
    ├── ponytail-gain/
    ├── ponytail-help/
    ├── ponytail-review/
    └── scroll-craft/
```

---

## License

Distributed under the [MIT License](LICENSE). Individual skill modules remain under the copyright and license of their respective authors.
