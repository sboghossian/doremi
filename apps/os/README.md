# Doremi OS

The local desktop app. Tauri v2 (Rust core + Vanilla TS frontend). macOS first.

For the architecture, latency budget, and stack rationale, see [ARCHITECTURE.md](ARCHITECTURE.md).

## Quickstart

```bash
# Prereqs: Rust 1.70+, Node 18+, pnpm
pnpm install
pnpm tauri dev
```

This opens a development window with hot-reload on the frontend (Vite) and the Rust backend (recompile on save).

## Build

```bash
pnpm tauri build
# Output: src-tauri/target/release/bundle/macos/Doremi.app
```

## Layout

```
apps/os/
├── src/                # Vanilla TS frontend (will host MediaPipe Hands, Studio/Record views)
├── src-tauri/          # Rust core (audio engine, brick loader, MIDI, camera)
├── ARCHITECTURE.md     # Why Tauri, latency budget, full system diagram
├── package.json        # Frontend deps
└── tsconfig.json
```

## What's coming

See [`../../tasks/todo.md`](../../tasks/todo.md) phases 2–5 for the buildout plan:

- **Phase 2** — Tauri shell, camera permission, MediaPipe Hands integration, basic soundfont playback
- **Phase 3** — Record session view with Spotify embed + capture stream
- **Phase 4** — Brick loader (`~/Doremi/bricks/`)
- **Phase 5** — Ollama integration for post-session gesture clustering
