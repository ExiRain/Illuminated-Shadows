# Illuminated Shadows

2D pixel-art action platformer. Vaelor, a masked vampire who consumes souls, seeks sainthood. Demo target: New Year 2027.

- **Design (source of truth):** [Notion → PROJECTS → Illuminated Shadows](https://app.notion.com/p/4119e31fc38a810eab25f3d7769bfe04)
- **Tasks:** [Trello board](https://trello.com/b/xuMOOyix/illuminated-shadow)

## Setup

1. Install [Godot 4.7.2](https://godotengine.org/download) (standard build, not .NET).
2. Install [Git LFS](https://git-lfs.com) and run `git lfs install` once.
3. Clone, then open `project.godot` in Godot.
4. VS Code: install the recommended **godot-tools** extension and point it at the running editor (Editor Settings → Text Editor → External).

## Project settings

- 640×360 viewport, integer scaling to 1280×720 window, Nearest filtering, pixel snap, 2D HDR (glow).
- Input actions: `move_left/right/up/down`, `jump`, `attack`, `evade`, `skill`, `drain`, `interact`, `pause` (keyboard + gamepad).
- Physics layers: world, player, enemy, player_hurtbox, enemy_hurtbox, player_attack, enemy_attack, soul, interactable.

## Structure

```
assets/
  art/characters/{vaelor,mirko,eleana,villagers}   *_old / *_concept = pre-redraw reference
  art/{tilesets,props,backgrounds,ui,vfx}
  audio/{music,sfx,voice}
  fonts/
scenes/{player,enemies,bosses,npcs,levels,ui,common}
scripts/{autoload,components}
data/{moves,enemies,bosses}   # .tres resources: tunable values live here, not in code
addons/
```

## Rules

- Art, audio and fonts are stored with Git LFS (see `.gitattributes`).
- Never commit exported builds or raw recordings.
- Commit `.uid` files; ignore `.godot/`.
