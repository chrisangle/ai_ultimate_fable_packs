# Stick Figure Mythology — Per-scene refine prompt (V1)

Given ONE scene's narrator voice text, propose:

1. `character.pose` — one of: walking · talking · fighting · thinking · reacting
2. `character.expression` — one of: neutral · angry · shocked · sad · smug
3. `background.style` — one of: savanna · cave · mountain · sea · village · abstract
4. A concise 3–8 word `title` for the scene (never rendered — used for storyboard notes only).

Input:
- `voiceText`: `{{voiceText}}`
- Previous scene's pose/expression: `{{previous_pose_expression}}`

Output STRICT JSON, no other text:
```json
{ "pose": "…", "expression": "…", "background": "…", "title": "…" }
```
