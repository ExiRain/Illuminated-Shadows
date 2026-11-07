# Illuminated Shadows

2D pixel-art action platformer in Godot 4.7.2 (GDScript). Solo dev; Claude writes the code, I make art/audio.

## Sources of truth
- Design: Notion → PROJECTS → Illuminated Shadows (https://app.notion.com/p/4119e31fc38a810eab25f3d7769bfe04). Read the relevant Mechanics / Abilities / Characters / Enemies page before implementing a feature. Never invent rules; if Notion doesn't say, ask me.
- Tasks: Trello board (https://trello.com/b/xuMOOyix/illuminated-shadow), one card = one feature.

## Code rules
- Godot 4.7 APIs only (no Godot 3 syntax: no `yield`, no `KinematicBody2D`, no `export var`).
- Static typing everywhere (`var speed: float`, typed function signatures).
- Input only through action names from project.godot (move_left/right/up/down, jump, attack, evade, skill, drain, interact, pause). Never raw keys, never `ui_*`.
- Use the named physics layers from project.godot; never magic layer numbers.
- Tunable numbers (speeds, damage, faith, timings) live in Resource `.tres` files under `data/`, not hard-coded.
- Prefer signals and small components over deep inheritance; one script per scene root.
- Don't change project settings (resolution, filtering, input map, layers) without asking.
- Follow the existing patterns in the repo; if a new pattern is clearly better, update the nearby old code too so there is one style.
- Comments: none unless I ask.

## Verify before saying "done"
- Run Godot headless: `"C:\GODOT E\Godot_v4.7.2-stable_win64_console.exe" --headless --path . --quit-after 120` must show no errors.
- Run the code-review skill on the change.
- Small commits with clear messages. Never commit `.godot/`, builds, or recordings. Art/audio go through Git LFS.
