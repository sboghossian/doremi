# Doremi

> A new way to create music intuitively.

Doremi turns hand motion into music. A local-first desktop instrument that watches your gestures, learns your style, and lets you perform any instrument with just your hands — no keys, no strings, no notation.

**Status:** Early development. Building in public. v1 is for macOS.

---

## Monorepo

| Folder | What |
|---|---|
| [`apps/landing`](apps/landing) | Public landing page → [doremi.dashable.dev](https://doremi.dashable.dev) |
| [`apps/os`](apps/os) | The local Doremi OS app — Tauri (Rust + Web) desktop instrument |
| [`bricks`](bricks) | Community-contributable gesture packs, sound packs, skill mappings, song presets |
| [`docs`](docs) | Architecture, brick spec, the original Notion brain-dump |
| [`tasks`](tasks) | Living todo / roadmap |

## How it works (vision)

1. **Record** — Drop a Spotify link, hit record, move freely. Doremi captures your hands (MediaPipe, 21 finger joints), the audio you play, and the song's structure.
2. **Learn** — A local model (Ollama) clusters your gestures unsupervised and proposes mappings — *"bind a pinch to a snare?"*
3. **Perform** — Two hands, two instruments simultaneously, < 50 ms latency. MIDI out to your DAW. Or play the built-in soundfont library.

## The brick model

Everything that can be extended is a **brick** — a JSON manifest + assets:

- **gesture-pack** — landmark templates for recognizable hand motions
- **sound-pack** — samples or soundfont files
- **skill** — mapping from a gesture-pack to a sound-pack
- **song-preset** — a Spotify URL + recommended skill + tempo

Drop a brick in `~/Doremi/bricks/`, it live-reloads. Publish a brick via PR to this repo, the whole community gets it. See [CONTRIBUTING.md](CONTRIBUTING.md).

## v1 scope (in flight)

- [x] Vision & scope locked (2026-05-19)
- [x] Notion brain-dump preserved at [`docs/notion`](docs/notion)
- [x] Landing page first cut
- [ ] OS app scaffold (Tauri + MediaPipe Hands + soundfont playback)
- [ ] Record session: webcam + Spotify embed + capture stream
- [ ] Local LLM analysis loop (Ollama)
- [ ] First default gesture-pack + sound-pack bricks

## License

[MIT](LICENSE). Use it, fork it, sell it. Contribute back if you can — that's the spirit.

## Credits

Started as a 21-month Notion brain dump. Owe-it-to-yourself moment courtesy of [@stephane](https://github.com/sboghossian).
