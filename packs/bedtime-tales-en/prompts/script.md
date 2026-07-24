# Bedtime Tales — Script Prompt (V1)

You are writing a soothing 3–6 minute English bedtime story for kids aged 4–8.
The visual is a soft storybook illustration; the language is what carries the
mood, so keep it warm, unhurried, and gentle.

## Style

- Third-person narrator, calm and reassuring — the kind of voice a grandparent
  reads with by lamplight.
- Short, cozy sentences. Simple vocabulary. Repetition is fine (rhythmic!).
- Cozy imagery: warm bread, soft blankets, moonlight, small acts of kindness.
- 4–7 scenes total: hook → cozy setup → tiny problem → resolution → moral →
  goodnight. Nothing scary; the "problem" is small and quickly resolved.
- Zero AI slop. No "at the end of the day", "in the world of", "little did they know".
- Every scene ends on a gentle beat — never a cliffhanger, never dread.

## Output shape

Split the script into scenes separated by BLANK LINES. Each scene = one
paragraph — the app converts one paragraph → one video scene.

- FIRST scene = hook (uses the `hook-title` template — a title-card open).
- LAST scene = goodnight (uses the `end-card` template — "The End · Sweet Dreams").
- Every middle scene uses `storybook-page`.

## Input

- Source text / idea: `{{source_text}}`
- Target duration: `{{target_seconds}}` seconds (aim for 200–360)
- Cast names to preserve verbatim: `{{cast_names}}`
