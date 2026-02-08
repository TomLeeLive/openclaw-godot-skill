# 🐾 OpenClaw Godot Skill

Companion skill for the [OpenClaw Godot Plugin](https://github.com/TomLeeLive/openclaw-godot-plugin). Provides AI workflow patterns and gateway extension for Godot Editor control.

## Installation

```bash
# Clone to OpenClaw workspace
git clone https://github.com/TomLeeLive/openclaw-godot-skill.git ~/.openclaw/workspace/skills/godot-plugin

# Install gateway extension
cd ~/.openclaw/workspace/skills/godot-plugin
./scripts/install-extension.sh

# Restart gateway
openclaw gateway restart
```

## What's Included

```
godot-plugin/
├── SKILL.md           # AI workflow guide (30 tools)
├── extension/         # Gateway extension (required)
│   ├── index.ts
│   ├── openclaw.plugin.json
│   └── package.json
├── scripts/
│   └── install-extension.sh
└── references/
    └── tools.md       # Detailed tool documentation
```

## Components

| Component | Purpose | Location |
|-----------|---------|----------|
| **Gateway Extension** | Enables `godot_execute` tool | `~/.openclaw/extensions/godot/` |
| **Skill** | AI workflow patterns | `~/.openclaw/workspace/skills/godot-plugin/` |
| **Godot Plugin** | Godot Editor addon | [openclaw-godot-plugin](https://github.com/TomLeeLive/openclaw-godot-plugin) |

## Quick Verify

```bash
# Check extension loaded
openclaw godot status

# Check skill available
ls ~/.openclaw/workspace/skills/godot-plugin/SKILL.md
```

## Requirements

- [OpenClaw](https://github.com/openclaw/openclaw) 2026.2.3+
- [OpenClaw Godot Plugin](https://github.com/TomLeeLive/openclaw-godot-plugin) in Godot

## License

MIT License - See [LICENSE](LICENSE)
