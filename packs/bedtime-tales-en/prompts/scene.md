# Bedtime Tales — Per-scene refine prompt (V1)

Given ONE scene's narrator voice text, propose:

1. A gentle 3–8 word `heading` for the storybook page (rendered above the copy;
   sentence-case, no punctuation at the end).
2. Whether this scene fits `storybook-page` (default), `hook-title` (only for
   the very first scene), or `end-card` (only for the very last scene).

Keep the tone cozy — nothing loud, nothing anxious.

Input:

- voiceText: `{{voice_text}}`
- order: `{{order}}` of `{{total}}`
