# Doremi OS

The local desktop app. macOS first. Tauri (Rust core + Web frontend).

> **Status:** Not yet scaffolded. Architecture frozen, code coming next.

## Architecture

```
┌─────────────────────────────────────────────────┐
│  Tauri shell (Rust)                             │
│  ├─ Window, menu, file I/O                      │
│  ├─ AVFoundation camera (macOS)                 │
│  ├─ CoreAudio output, low-latency thread        │
│  ├─ Soundfont engine (oxisynth or similar)      │
│  ├─ MIDI out (coremidi)                         │
│  ├─ Brick loader (file watcher on ~/Doremi/bricks/) │
│  └─ Ollama HTTP client                          │
├─────────────────────────────────────────────────┤
│  WebView (TypeScript + Vite)                    │
│  ├─ MediaPipe Hands (21 joints, 30+ FPS)        │
│  ├─ Studio view (live performance)              │
│  ├─ Record view (Spotify embed + capture)       │
│  ├─ Brick browser & editor                      │
│  └─ Skill review UI (post-session)              │
├─────────────────────────────────────────────────┤
│  Ollama (separate process)                      │
│  └─ Post-session gesture clustering & analysis  │
└─────────────────────────────────────────────────┘
```

## Why Tauri (not Electron, not native Swift)

| | Tauri | Electron | Native Swift |
|---|---|---|---|
| Audio latency | ✅ Rust thread, < 10 ms | ❌ JS event loop | ✅ Best |
| Hand tracking | ✅ MediaPipe.js | ✅ MediaPipe.js | ⚠️ CoreML port |
| Community contribs | ✅ TS bricks | ✅ TS bricks | ❌ Swift only |
| Cross-platform later | ✅ Free | ✅ Free | ❌ Locked in |
| Bundle size | ✅ ~15 MB | ❌ ~150 MB | ✅ ~10 MB |

## Setup (when scaffolded)

```bash
# Prereqs: Rust toolchain, Node, pnpm
rustup --version  # 1.70+
node --version    # 18+

cd apps/os
pnpm install
pnpm tauri dev
```

Coming in the next phase. See [`tasks/todo.md`](../../tasks/todo.md) phase 2.

## Latency budget

End-to-end target: **< 50 ms** from gesture to sound.

| Stage | Budget |
|---|---|
| Camera capture (30 FPS) | ~16 ms |
| MediaPipe inference | ~10 ms |
| Gesture classification (on-device) | ~5 ms |
| Tauri IPC → Rust audio thread | ~2 ms |
| Soundfont synth + CoreAudio | ~10 ms |
| **Total** | ~43 ms |

Achievable. Native synths can do <10 ms. The variable is MediaPipe — depends on whether we use the lite or full model.
