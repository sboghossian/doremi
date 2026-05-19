# Notion brain-dump — structured insights

Distilled from `notion-export.md` on 2026-05-19. The brain dump lived from 2024-01-10 → 2025-09-28 (~21 months) under `/Portfolio` in Notion. Most of the page is AI-generated business-plan scaffolding. The gold is one toggle called **"Process of thinking"** (line 177 of the clean export).

---

## 1. Core vision

Doremi is conceived as a "motion-powered music maker" — a digital musical instrument that transforms body movements and gestures into music via customizable "motion hands," letting a single user play many instruments at once across a 360° space divided into instrument environments.

Verbatim:
> "DoReMi is a revolutionary music instrument company designed to enable simultaneous music creation with multiple instruments. It features customizable motion hands, divided environments for instruments, and capabilities like broadcasting music, recording voice-over-the-music, and connecting to external devices."

Emotional/launch voice:
> "an extension of your artistic soul... Every gesture you make... comes alive as a melody, a beat, or a harmony"
> "for anyone who feels music in their bones... Whether you're dancing, walking, or even standing still."

## 2. Timeline

- Created: 2024-01-10
- Last edited: 2025-09-28
- ~21 months of brain-dumping, zero engineering decisions
- Build phase started: **2026-05-19**

## 3. The real backlog — original 10-point prompt

The only place Stephane is thinking out loud (not auto-generating template):

1. **Per-gesture, per-note customization** — *"motion hands can be customized for every musical note from an instrument, you previously record or download from public sources"*
2. **360° spatial zones** — *"environment surrounding you 360 is divided into multiple instruments"* ← most distinctive
3. **Broadcasting & remote-live sessions**
4. **Voice-over with effects** via embedded mic
5. **Open-source content marketplace** for notes, lyrics, instruments
6. **Universal export** to any format/platform
7. **External device control** (implies MIDI/IoT)
8. **Environmental data sonification** ⚠️ — *"Automatically create music from the data collected from your environment"* — buried, never expanded, the most novel thread
9. **Real-time editing tools**
10. **Mobile companion app**

## 4. Names that have lived

- **DoReMi / Do.Re.Mi** — primary, icon 🪕
- **MusicBox** — earliest working name, discarded
- **DO • RE • MO** — concept render variant, tied to tagline *"MO is Feel music your way"*
- **DO • Re • MI** — variant on device render (literal solfège)

→ **v1 locked: DO • RE • MO** (pending one-word confirm from Stephane vs MI)

## 5. Aesthetic signals (concept-render prompt)

- *"sleek, cylindrical smart music player device with a matte light gray body, soft, rounded dome top"*
- *"circular touch-sensitive display glowing with a pastel gradient (purple, pink, yellow)"*
- *"tactile metallic band wraps around the middle, resembling a speaker mesh"*
- *"modern sans-serif font, clean and minimalistic in a gradient light gray, shot with soft studio lighting and no shadows"*

Territory: **Apple / Teenage Engineering minimalism.** Note: the render shows a smart-speaker form factor, not a wearable — hardware form is unsettled.

Brand emotional arc (user-journey doc): *Curiosity → Eagerness → Accomplishment → Inspiration → Pride.*

## 6. Personas declared

- Professional musicians (innovative performance tools)
- Music enthusiasts and hobbyists (accessible creation)
- Content creators / social-media influencers (real-time production)
- DJs
- Music schools & online learning platforms
- Launch copy goes broader: *"anyone who feels music in their bones."*

Accessibility hinted but never made explicit — *"Traditional instruments are expensive and difficult to learn"* is the closest.

## 7. Competitors & prior art named

| Player | What Stephane wrote |
|---|---|
| **Roli** (Seaboard, Blocks) | *"focused on tactile, touch-based music creation. DoReMi differentiates by emphasizing motion-based control and hands-free creation."* |
| **Ableton Live** | *"a more immersive, real-time, and accessible interface that doesn't require traditional equipment."* |
| **Artiphon** | *"all-in-one instruments... DoReMi's edge is in its motion-controlled interface and broadcast/voice-over features."* |
| **MiMu Gloves** (Imogen Heap) | *"High-end wearable technology... DoReMi offers a more affordable, mass-market product."* |

Potential acquirers named: Yamaha, Ableton, Native Instruments.
Ecosystem partners named: Oculus, Magic Leap.
Demo events: NAMM, SXSW.
Distribution targets: TikTok, YouTube.

## 8. Hardware contemplated

- A wearable motion device priced **$200–$300**
- Embedded microphone
- Mobile companion app
- Concept renders show a smart-speaker form factor (not a wearable)
- No sensor type specified anywhere

## 9. Critical risk Stephane already flagged to himself

- **Load-bearing assumption:** *"Users will embrace motion-based music tools."*
- **Risk areas:** *"Technical reliability, user adoption, legal/IP issues."*

## 10. What's missing from the dump (gaps the v1 build must close)

- Zero engineering picks (no MediaPipe / OpenCV / Web MIDI / etc. ever named)
- No sensor decision (camera vs wearable vs IMU)
- No audio stack decision (samples vs synth vs MIDI-out)
- No latency target
- No app stack (Electron vs native vs web)
- No license decision
- Accessibility never made explicit (despite being a natural fit)
- The environmental-sonification idea (#8 of the original 10) is never expanded — biggest sleeper concept

These gaps were closed in the 2026-05-19 scoping session — see `~/.claude/projects/.../memory/doremi-v1-decisions.md`.
