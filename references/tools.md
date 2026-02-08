# Godot Plugin Tools Reference

Complete parameter reference for all 30 tools.

## Scene Tools

### scene.getCurrent
Get current scene info. No parameters.
Returns: name, path, nodeCount

### scene.list
List all scenes in project. No parameters.
Returns: array of scene paths (.tscn, .scn)

### scene.open
Open a scene.
```json
{
  "path": "res://scenes/main.tscn"
}
```

### scene.save
Save current scene. No parameters.

---

## Node Tools

### node.find
Find nodes in scene.
```json
{
  "name": "Player",       // Find by name (substring match)
  "type": "Sprite2D",     // Find by exact type
  "group": "enemies"      // Find by group
}
```

### node.create
Create a new node.
```json
{
  "type": "Node2D",       // Node type (see list below)
  "name": "MyNode",       // Node name
  "parent": "Parent/Path" // Optional parent path
}
```

Supported types: Node, Node2D, Node3D, Sprite2D, Sprite3D, CharacterBody2D, CharacterBody3D, RigidBody2D, RigidBody3D, Area2D, Area3D, Camera2D, Camera3D, DirectionalLight3D, Label, Button, Control

### node.delete
Delete a node.
```json
{
  "path": "Parent/NodeToDelete"
}
```

### node.getData
Get detailed node info.
```json
{
  "path": "Player"        // Empty for scene root
}
```
Returns: name, type, path, children, groups, position/rotation/scale (for spatial nodes)

### node.getProperty
Get node property.
```json
{
  "path": "Player",
  "property": "modulate"  // Empty to get all properties
}
```

### node.setProperty
Set node property.
```json
{
  "path": "Player",
  "property": "modulate",
  "value": [1, 0, 0, 1]
}
```

---

## Transform Tools

### transform.setPosition
Set node position.
```json
{
  "path": "Player",
  "x": 100,
  "y": 200,
  "z": 0        // For Node3D only
}
```

### transform.setRotation
Set node rotation.
```json
{
  "path": "Player",
  "degrees": 45,          // For Node2D
  "x": 0, "y": 90, "z": 0 // For Node3D
}
```

### transform.setScale
Set node scale.
```json
{
  "path": "Player",
  "x": 2,
  "y": 2,
  "z": 1        // For Node3D only
}
```

---

## Editor Tools

### editor.play
Play scene.
```json
{
  "scene": "res://levels/level1.tscn"  // Optional, plays current scene if empty
}
```

### editor.stop
Stop playing. No parameters.

### editor.pause
Toggle pause. No parameters.

### editor.getState
Get editor state. No parameters.
Returns: isPlaying, version, projectName, editedScene

---

## Debug Tools

### debug.screenshot
Capture viewport screenshot.
```json
{
  "2d": false   // true for 2D viewport, false for 3D
}
```
Returns: path to saved PNG

### debug.tree
Get scene tree as text.
```json
{
  "depth": 3    // Max depth (default: 3)
}
```

### debug.log
Print to output.
```json
{
  "message": "Hello",
  "type": "log"    // "log", "warning", "error"
}
```

---

## Script Tools

### script.list
List GDScript files.
```json
{
  "folder": "res://scripts"  // Optional, defaults to res://
}
```

### script.read
Read script content.
```json
{
  "path": "res://scripts/player.gd"
}
```

---

## Resource Tools

### resource.list
List resources by extension.
```json
{
  "folder": "res://",
  "extension": ".png"  // Optional filter
}
```
