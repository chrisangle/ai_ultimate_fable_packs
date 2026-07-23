# ai_ultimate_fable_packs

Style catalog for [ai-video-ultimate](https://github.com/chrisangle/ai_ultimate)'s
**Fable Studio** — each pack is a self-contained visual style + narrator voice profile the app
downloads on demand.

## Repo layout

```
ai_ultimate_fable_packs/
├── README.md
├── LICENSE (MIT)
├── registry.json                          ← index of all published packs
└── packs/
    ├── stick-mythology-en/                ← one folder per pack
    │   ├── pack.json                      ← manifest (FablePackManifest schema)
    │   ├── templates/*.html               ← scene layouts (HyperFrames-rendered)
    │   ├── voice/ref-narrator-*.mp3       ← voice-clone reference clip
    │   ├── sfx/<category>/*.mp3           ← optional SFX library
    │   ├── style/tokens.css               ← CSS color palette
    │   ├── sources/*.txt                  ← optional public-domain corpus
    │   └── prompts/{script,scene}.md      ← LLM prompt templates
    └── self-improvement-vn/
```

## How the app consumes this

1. First-time user opens Fable Studio → step 1 offers "Fetch style catalog" →
   the app `git clone`s this repo into
   `<userData>/fable-packs/.source/` (macOS: `~/Library/Application Support/ai-ultimate/fable-packs/.source/`).
2. Available packs are listed from `registry.json`.
3. User clicks "Install & use" on a pack → the app copies `packs/<packId>/` into
   `<userData>/fable-packs/<packId>/` (materialized so a later `git pull` on the
   source can never half-swap files under an in-flight render).
4. Updating a pack = `git pull` in the source + re-copy — the manifest snapshot
   frozen inside the user's `fable_packs_installed` DB row is unchanged until
   the next update.

## Adding a pack

1. Create `packs/<pack-id>/pack.json` following the `FablePackManifest` schema
   (see either bundled pack for a working example).
2. Add HTML templates under `templates/` — each `templateId` referenced by
   scenes maps to `<templates>/<templateId>.html`. Fill slots via
   `data-composition-variable` attributes.
3. Ship a real voice reference clip (30 seconds of a single speaker, no
   background music) at the path declared by `voice.referenceClip`.
4. Register the pack in `registry.json`.
5. `git push` — the app picks it up on the next "Fetch style catalog" from any
   user's device.

## License

MIT — free to fork, adapt, or ship your own packs on top.
