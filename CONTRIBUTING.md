# Contributing to Doremi

Doremi is built in public, brick by brick. The fastest way to contribute is to add a **brick** — a small, self-contained extension that ships with no code changes to the core app.

## The four brick types

Every brick is a folder under `bricks/<type>/<slug>/` containing a `brick.json` manifest and any assets.

### 1. `gesture-pack`

A library of recognizable hand gestures. Each gesture is defined by a sequence of MediaPipe Hand landmarks (21 points × 3 axes per hand).

```
bricks/gestures/drum-basics/
├── brick.json
├── kick.landmarks.json
├── snare.landmarks.json
├── hihat.landmarks.json
└── README.md
```

```json
{
  "type": "gesture-pack",
  "slug": "drum-basics",
  "name": "Drum Kit Basics",
  "version": "0.1.0",
  "author": "@yourhandle",
  "license": "MIT",
  "description": "5 essential drum-kit gestures: kick, snare, hi-hat, tom, crash.",
  "gestures": [
    { "id": "kick", "file": "kick.landmarks.json", "modality": "discrete" },
    { "id": "snare", "file": "snare.landmarks.json", "modality": "discrete" }
  ]
}
```

### 2. `sound-pack`

A collection of audio samples or a soundfont (.sf2). What gets played.

```
bricks/sounds/lofi-drums/
├── brick.json
├── samples/
│   ├── kick-808.wav
│   └── snare-vinyl.wav
└── README.md
```

```json
{
  "type": "sound-pack",
  "slug": "lofi-drums",
  "name": "Lo-Fi Drum Kit",
  "format": "samples",
  "samples": {
    "kick": "samples/kick-808.wav",
    "snare": "samples/snare-vinyl.wav"
  }
}
```

`format` can also be `"soundfont"` with a single `file: "kit.sf2"` field.

### 3. `skill`

A mapping. Connects a `gesture-pack` to a `sound-pack`. This is the "playable instrument" a user binds to a hand.

```json
{
  "type": "skill",
  "slug": "lofi-drumming",
  "name": "Lo-Fi Drumming",
  "gestures": "drum-basics@0.1.0",
  "sounds": "lofi-drums@0.1.0",
  "mappings": [
    { "gesture": "kick", "sample": "kick" },
    { "gesture": "snare", "sample": "snare" }
  ]
}
```

### 4. `song-preset`

A starting point for a recording session: a Spotify (or local audio) URL, recommended skill, tempo hint.

```json
{
  "type": "song-preset",
  "slug": "blinding-lights",
  "name": "Blinding Lights — drumming along",
  "spotify": "https://open.spotify.com/track/0VjIjW4GlUZAMYd2vXMi3b",
  "tempo": 171,
  "recommended_skill": "lofi-drumming@0.1.0"
}
```

## Submitting a brick

1. Fork the repo.
2. Add your brick under the right folder.
3. Open a PR. Include a short README in your brick folder with **why** you made it and a 10–30 sec demo clip if you have one.
4. We'll review for: schema validity, license compatibility (MIT-compatible), and that it loads cleanly in the OS app.

## Contributing to the core app

Core code lives in `apps/os` (Tauri + Rust + Web frontend) and `apps/landing` (static HTML for now).

- Prefer **opening an issue first** for anything that touches the audio engine, the gesture pipeline, or the brick loader — these are load-bearing.
- Small wins (typo fixes, copy improvements, doc clarifications) — just PR directly.
- Style: TypeScript strict, no `any`. Rust idiomatic. Tailwind, no inline styles.

## Code of conduct

Be kind. Doremi is for everyone who feels music in their bones — that's the whole point.
