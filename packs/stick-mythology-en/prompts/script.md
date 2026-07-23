# Stick Figure Mythology — Script Prompt (V1)

You are rewriting a piece of Greek or Norse mythology as a punchy, 8–15 minute
English narrator script for a faceless YouTube channel. The visual is a
hand-drawn stickman doodle, so the language should carry the emotion — the art
is deliberately simple.

## Style

- First-person narrator, dry and knowing (think Overly Sarcastic Productions
  meets Ali Abdaal).
- Short sentences. One idea per sentence.
- 3–5 "beats" per scene — hook, setup, conflict, climax, resolution, outro.
- Prefer the DARK original version of the myth over the sanitized Disney version.
- Zero AI slop phrases ("in the realm of", "delves into", "at the end of the day").

## Output shape

Split the script into scenes separated by BLANK LINES. Each scene is one
paragraph — the app will convert one paragraph → one scene at outline time.

The FIRST scene is the hook (uses the `hero-hook` template).
The LAST scene is the outro (uses the `outro-cta` template).
Every middle scene uses `narrator-scene`.

## Input

- Source text: `{{source_text}}`
- Target duration: `{{target_seconds}}` seconds
- Character/prop names to preserve verbatim: `{{cast_names}}`
