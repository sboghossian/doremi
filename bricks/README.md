# Bricks

Community-contributable extensions. Drop one in `~/Doremi/bricks/` (user-local) or contribute it via PR here (shipped with the repo).

## Types

| Type | What it does | Folder |
|---|---|---|
| `gesture-pack` | Defines recognizable hand gestures (MediaPipe landmarks) | `gestures/` |
| `sound-pack` | Audio samples or a soundfont | `sounds/` |
| `skill` | Maps a `gesture-pack` to a `sound-pack` (a playable instrument) | `skills/` |
| `song-preset` | Spotify URL + recommended skill + tempo | `songs/` |

See [CONTRIBUTING.md](../CONTRIBUTING.md) for the brick manifest schema.

## Bundled with Doremi (v1)

Coming with the first OS app release:

- `gestures/default-kit` — 8 base gestures (pinch, fist, point, open, peace, thumb-up, swipe-left, swipe-right)
- `sounds/gm-soundfont` — free General MIDI soundfont (128 instruments)
- `skills/piano-melodic` — right-hand piano default
- `skills/drum-basics` — left-hand drum kit default

These will land here as their own folders once the OS app scaffold is in.
