# News Poster (EN / VN) — Attribution

## Templates

The 11 poster templates in `templates/` (`frame-liquid-bg-hero`,
`frame-vignelli`, `frame-pentagram-stat`, `frame-bold-poster`,
`frame-build-minimal`, `frame-creative-voltage`, `frame-glitch-title`,
`frame-aicoding-list`, `frame-aicoding-comparison`, `frame-logo-outro`,
`frame-statement-outro`) were **forked from**:

**huytranvan2010/AI-auto-generate-video**
https://github.com/huytranvan2010/AI-auto-generate-video
Licensed MIT (verified 2026-07-24 via GitHub `/license` API).
Copyright © 2026 AI Coding · Copyright © 2026 Ho Quang Hai.

Some templates in the huytranvan collection themselves vendor prior art:

- `frame-liquid-bg-hero` — adapted from **nexu-io/html-video**
  (Apache 2.0). https://github.com/nexu-io/html-video

## Render engine

The pack HTML files are rendered by **HyperFrames** by HeyGen
(https://github.com/heygen-com/hyperframes). The Fable Studio app invokes
`npx hyperframes@0.6.94 render` as a subprocess — HyperFrames itself is
NOT bundled or redistributed by this pack.

## Modifications by aivideoultimate (fork)

- Added Fable pack manifest (`pack.json`) with bilingual `name`/`description`
  and full `templateCatalog` schema for the app + LLM prompt renderer.
- Standardised typography for Vietnamese (news-poster-vn): Be Vietnam Pro
  + Inter Tight fallback.
- Extended every template's inline script with the Fable "Way Y" character-
  identity fallback (auto-inject `.auto-char-badge` for reserved slots
  `characterName` / `leftName` / `rightName`). Class `.auto-char-badge` CSS
  added per template — see `src/shared/fable-pack/template-contract.ts`
  in the main app repo.
- Refined `body { background: <color> }` → `body { background: transparent }`
  per Fable Template Contract v3 (colors live on `#root`).
- New `prompts/script.md` (V2 strategy) + `prompts/scene.md` (V2 tactics)
  for the news-poster niche.

Everything under `packs/news-poster-*/` remains MIT-licensed, matching the
upstream. See the repo-root `LICENSE` for full text.
