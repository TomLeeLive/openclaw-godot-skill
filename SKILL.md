---
name: godot-plugin
description: Control Godot Editor via OpenClaw Godot Plugin. Use for Godot game development tasks including scene management, node manipulation, debugging, and editor control. Triggers on Godot-related requests like inspecting scenes, creating nodes, taking screenshots, or controlling the editor.
---

# Godot Plugin Skill

Control Godot 4.x Editor through 30 built-in tools.

## Quick Reference

### Core Tools

| Category | Key Tools |
|----------|-----------|
| **Scene** | `scene.getCurrent`, `scene.list`, `scene.open` |
| **Node** | `node.find`, `node.create`, `node.delete`, `node.getData` |
| **Transform** | `transform.setPosition`, `transform.setRotation` |
| **Debug** | `debug.tree`, `debug.screenshot`, `debug.log` |
| **Editor** | `editor.play`, `editor.stop`, `editor.getState` |

## Common Workflows

### 1. Scene Inspection

```
godot_execute: debug.tree {depth: 3}
godot_execute: scene.getCurrent
```

### 2. Find & Modify Nodes

```
godot_execute: node.find {name: "Player"}
godot_execute: node.getData {path: "Player"}
godot_execute: transform.setPosition {path: "Player", x: 100, y: 200}
```

### 3. Create Nodes

```
godot_execute: node.create {type: "Sprite2D", name: "Enemy", parent: "Enemies"}
godot_execute: transform.setPosition {path: "Enemies/Enemy", x: 500, y: 300}
```

### 4. Editor Control

```
godot_execute: editor.play                    # Play current scene
godot_execute: editor.play {scene: "res://levels/level1.tscn"}  # Play specific scene
godot_execute: editor.stop                    # Stop playing
godot_execute: editor.getState                # Check state
```

## Tool Categories

### Scene (4 tools)
- `scene.getCurrent` - Get current scene info
- `scene.list` - List all .tscn/.scn files
- `scene.open` - Open scene by path
- `scene.save` - Save current scene

### Node (6 tools)
- `node.find` - Find by name, type, or group
- `node.create` - Create node (Node2D, Node3D, Sprite2D, etc.)
- `node.delete` - Delete node by path
- `node.getData` - Get node info, children, transform
- `node.getProperty` - Get property value
- `node.setProperty` - Set property value

### Transform (3 tools)
- `transform.setPosition` - Set position {x, y} or {x, y, z}
- `transform.setRotation` - Set rotation (degrees)
- `transform.setScale` - Set scale

### Editor (4 tools)
- `editor.play` - Play current or custom scene
- `editor.stop` - Stop playing
- `editor.pause` - Toggle pause
- `editor.getState` - Get playing state, version, project name

### Debug (3 tools)
- `debug.screenshot` - Capture viewport
- `debug.tree` - Get scene tree as text
- `debug.log` - Print message

### Script (2 tools)
- `script.list` - List .gd files
- `script.read` - Read script content

### Resource (1 tool)
- `resource.list` - List files by extension

## Node Types for Creation

| Type | Description |
|------|-------------|
| `Node` | Base node |
| `Node2D` | 2D spatial |
| `Node3D` | 3D spatial |
| `Sprite2D` | 2D sprite |
| `Sprite3D` | 3D sprite |
| `CharacterBody2D` | 2D character |
| `CharacterBody3D` | 3D character |
| `RigidBody2D` | 2D physics |
| `RigidBody3D` | 3D physics |
| `Area2D` | 2D area |
| `Area3D` | 3D area |
| `Camera2D` | 2D camera |
| `Camera3D` | 3D camera |
| `Label` | UI text |
| `Button` | UI button |

## Tips

### Finding Nodes
```
node.find {name: "Player"}      # By name substring
node.find {type: "Sprite2D"}    # By exact type
node.find {group: "enemies"}    # By group
```

### Node Paths
- Root node: leave path empty or use node name
- Child: `"Parent/Child"`
- Deep: `"Parent/Child/GrandChild"`
