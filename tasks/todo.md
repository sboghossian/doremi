# Doremi — Working TODO

Living plan. Updated 2026-05-19.

## ✅ Phase 0 — Scoping

- [x] Scrape Notion brain-dump (preserved at `docs/notion/`)
- [x] Save brainstormed ideas to memory
- [x] Feasibility analysis (camera+MediaPipe, soundfonts, Tauri, Ollama)
- [x] Ask 25 scoping questions
- [x] Lock v1 decisions (camera-only, macOS, Tauri, MIT, DO • Re • MI, parallel build)

## ✅ Phase 1 — Foundation

- [x] Monorepo skeleton (`apps/`, `bricks/`, `docs/`, `tasks/`)
- [x] Root README + LICENSE (MIT) + CONTRIBUTING (brick spec) + .gitignore
- [x] Landing page first cut (`apps/landing/index.html`)
- [x] Three-wave logo (inline SVG)
- [x] `git init` + first commit
- [x] GitHub remote: [github.com/sboghossian/doremi](https://github.com/sboghossian/doremi)
- [x] Cloudflare Pages project `doremi` created
- [x] Landing deployed: [doremi-1wu.pages.dev](https://doremi-1wu.pages.dev)
- [ ] **Stephane:** attach `doremi.dashable.dev` custom domain via Cloudflare dashboard (30-sec step)
- [ ] Favicon + OG image
- [ ] Wire email-capture to real backend (later)

## 🟡 Phase 2 — OS app v0 (in progress)

- [x] Rust 1.95 installed via rustup
- [x] Tauri v2 scaffolded at `apps/os` (vanilla-ts, identifier `dev.dashable.doremi-os`)
- [x] `pnpm install` complete
- [ ] First smoke test: `pnpm tauri dev` opens a window
- [ ] Tauri app shell: window, dev server, system permissions
- [ ] Camera permission + webcam feed (AVFoundation via Tauri)
- [ ] MediaPipe Hands integration → live hand skeleton overlay
- [ ] Audio engine: soundfont playback via Rust `oxisynth` or JS `soundfont-player`
- [ ] First gesture → sound binding (hardcoded pinch = kick to prove the loop)
- [ ] Latency measurement harness (target < 50 ms end-to-end)

## ⚪ Phase 3 — Record session

- [ ] Spotify embed iframe in the record view
- [ ] Local audio file fallback (Spotify only allows embed, no audio API)
- [ ] Record button captures: webcam video, hand-pose stream (JSON), audio mix, Spotify metadata
- [ ] Session output format → `~/Doremi/sessions/<timestamp>/`

## ⚪ Phase 4 — Brick system

- [ ] Brick loader (watches `~/Doremi/bricks/` and the bundled repo bricks)
- [ ] Default gesture-pack: 8 base gestures (pinch, fist, point, open, peace, thumb-up, swipe-left, swipe-right)
- [ ] Default sound-pack: free GM soundfont (~5 MB, 128 instruments)
- [ ] Default skill: piano-melodic-default (right hand) + drum-basics (left hand)
- [ ] Brick validator (CLI: `doremi validate ./my-brick/`)

## ⚪ Phase 5 — LLM analysis

- [ ] Detect local Ollama install, prompt if missing
- [ ] Pick base model (Llama 3.2 3B or Phi 3.5 — small enough to run alongside the app)
- [ ] Post-session analysis pipeline: feed gesture stream + audio markers → cluster prompt → JSON skill suggestion
- [ ] In-app review UI: accept / reject / edit suggested gesture bindings

## ⚪ Phase 6 — Marketplace prep

- [ ] Brick directory in repo: `bricks/<type>/<slug>/`
- [ ] CI: validate every brick on PR
- [ ] Static brick browser on landing page (read `bricks/` from GitHub API)
- [ ] In-app brick install (clone from URL or browse marketplace)

## Open questions for Stephane

- [ ] GitHub org/handle for the public repo? (Use `sboghossian/doremi`?)
- [ ] Where does dashable.dev live? (Cloudflare Pages? Vercel? Custom server?)
- [ ] Rust toolchain installed? (Run `rustup --version` to check)
- [ ] Email-capture backend for landing-page form? (Resend? Loops? a Google Sheet?)
- [ ] "Prism" from the first message — what was that referring to?
