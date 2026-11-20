# Antigravity Essentials

Curated skill bundle for Google Antigravity. Focuses on token efficiency, full-stack software engineering, anti-slop rules, and natural Indonesian prose editing.

## Included Skills

- **jagoan**: Full-stack engineering, token compression (Caveman Lite), and pragmatic execution without conversational filler.  
  Author: [FuzailFr](https://github.com/FuzailFr)
- **humanizer-indonesia**: Indonesian text editing to eliminate AI cliches, machine-translation phrasing (*kalke*), and preserve author voice.  
  Author: [Adhi Pribadi](https://github.com/adhiprib/humanizer-indonesia)
- **anti-slop**: Comprehensive rule set and filters for code comment hygiene, accessible UI, mobile layouts, and humanized copy.  
  Author: [Miqdad Badjuber](https://github.com/miqdadbadjuber/anti-slop)

## Quick Install (Antigravity Prompt)

Salin 1 prompt di bawah ini dan kirimkan langsung ke agent Antigravity Anda:

```text
Pasang bundle skill dari https://github.com/FuzailFr/antigravity-essentials.git ke direktori plugins global Antigravity perangkat ini (~/.gemini/config/plugins/antigravity-essentials). Sesuaikan path sesuai OS (Windows/Linux/macOS), clone repo tersebut, lalu verifikasi bahwa folder skills di dalamnya sudah terpasang.
```

## Manual Install (Terminal)

Linux / macOS:
```bash
git clone https://github.com/FuzailFr/antigravity-essentials.git "$HOME/.gemini/config/plugins/antigravity-essentials"
```

Windows (PowerShell):
```powershell
git clone https://github.com/FuzailFr/antigravity-essentials.git "$env:USERPROFILE\.gemini\config\plugins\antigravity-essentials"
```

## Structure

```text
antigravity-essentials/
├── README.md
├── LICENSE
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

## License

MIT License. See [LICENSE](LICENSE) for details. Individual skills remain under copyright of their respective authors.
