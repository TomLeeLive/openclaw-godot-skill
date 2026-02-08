# OpenClaw Godot Skill

OpenClaw skill for controlling Godot Editor via [OpenClaw Godot Plugin](https://github.com/TomLeeLive/openclaw-godot-plugin).

## Installation

Copy to OpenClaw workspace:

```bash
cp -r . ~/.openclaw/workspace/skills/godot-plugin
```

## Requirements

- [OpenClaw](https://github.com/openclaw/openclaw) 2026.2.3+
- [OpenClaw Godot Plugin](https://github.com/TomLeeLive/openclaw-godot-plugin) installed in Godot

## Features

This skill provides guidance for 30 Godot control tools:

- **Scene Management** - Open, save, list scenes
- **Node Control** - Create, find, modify, delete nodes
- **Transform** - Position, rotation, scale
- **Debug Tools** - Screenshots, scene tree view
- **Editor Control** - Play, stop, pause

## Usage

The skill automatically activates for Godot-related tasks:

```
"Show me the scene tree"
"Create a Sprite2D named Enemy at (100, 200)"
"Play the game"
"Find all nodes in the 'enemies' group"
```

## Files

```
godot-plugin/
├── SKILL.md              # Main skill guide
└── references/
    └── tools.md          # Complete tool reference
```

## License

MIT License
