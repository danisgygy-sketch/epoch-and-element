# Remotion Art Direction — Shorts 001

Status: **specification only.** No Remotion project has been scaffolded and nothing has been rendered. The repository has no `package.json` yet; the skeleton is created in the next phase with the installed `remotion-create` skill.

**Brand source.** Colours and typefaces come from the EPOCH & ELEMENT Production Bible v0.1 (§4.3, §4.4), stored unchanged at `00_STUDIO/Production_Bible.md`.

## 1. Division of labour

| Blender (3D) | Remotion (2D) |
|---|---|
| Mechanisms, environments, macro and orbit shots, the evidence "ghosting" | Titles, typography, data labels, timeline strip, scientific diagrams, captions, transitions between 3D and 2D, the brand end card |

The rule: **if it explains, Remotion draws it; if it is a physical thing, Blender renders it.**

## 2. Composition

| Property | Value |
|---|---|
| ID | `Shorts001` |
| Size / fps | 1080 × 1920 · 30 |
| Duration | Nominal **1,440 frames (48.0 s)**; hard cap **1,650 frames (55.0 s)** (the studio's tolerance) |
| Data | `timeline.json` (scene and caption frames, derived from the narration timing) and the `.srt` in `captions/` |
| Layers (bottom → top) | 1 Blender plate (`OffthreadVideo` or image sequence) → 2 diagram layer → 3 data labels / leader lines → 4 titles → 5 captions → 6 end card |
| Audio | Out of scope for now (the studio will add it); the composition keeps empty audio tracks for VO, music and SFX |

Build it so the whole video is **data-driven**: scene start and end frames come from one JSON file, so re-timing to the real voice take means regenerating one file.

### Scene frames (150 wpm model, script v2; replace after the real take)

| Scene | Start frame | End frame | Duration |
|---|---|---|---|
| 01 The Hook | 0 | 205 | 205 |
| 02 Calculating the Sky | 205 | 423 | 218 |
| 03 Discovery | 423 | 650 | 227 |
| 04 The Mechanism Revealed | 650 | 915 | 265 |
| 05 What We Don't Know | 915 | 1172 | 257 |
| 06 Final Reveal | 1172 | 1440 | 268 |

## 3. Design system (from the Production Bible)

Colours (Bible §4.3) and typefaces (Bible §4.4) are the studio's. Sizes, safe areas and motion rules are this project's, within the Bible's guidance (§6).

| Token | Bible name | Hex | Use in Shorts 001 |
|---|---|---|---|
| `--navy` | Midnight Navy | `#101A2A` | Main dark background, scrims |
| `--deep-blue` | Deep Blue | `#172D46` | Background layers, plates, underwater tint |
| `--ivory` | Warm Ivory | `#F2EFE7` | Primary text |
| `--gold` | Antique Gold | `#D6AC62` | Historical accents and emphasis (stressed words, title rule) |
| `--cyan` | Scientific Cyan | `#56C6DF` | Diagrams, data, and the **reconstruction/hypothesis** layer and legend chip |
| `--red` | Muted Red | `#C76A62` | Not used in Shorts 001 (reserved for warnings and conflict) |

| Role | Typeface (Bible §4.4) | Use |
|---|---|---|
| Titles, headings, large numerals | **Space Grotesk** | Title, count-ups (82, 30), scene headings |
| Explanatory text, captions, subtitles | **Inter** | Burned-in captions, subtitle line |
| Technical labels, data, metadata | **IBM Plex Mono** | Dates ("c. 150–100 BCE"), the "SCIENTIFIC TERM" line, micro-labels, SIMPLIFIED ILLUSTRATION, legend chips |

The Bible asks to limit font families per video; this short uses all three, each in one role only.

Load fonts through Remotion's font support (see the installed `remotion-markup` `google-fonts.md` / `local-fonts.md`) and wait for them before rendering so no frame renders in a fallback font.

**Hierarchy (at 1080 px wide):** title 108–132 px · subtitle 44–52 px · data label 44–56 px · caption 54–62 px · micro-label (DRAMATIZED RECONSTRUCTION etc.) 30–34 px, never smaller. Minimum contrast against the plate: **4.5 : 1**, checked on the actual frames.

**Safe areas:** 64 px left; **120 px right** (Shorts icons); bottom **440 px** reserved for the Shorts interface. Captions sit at y ≈ 1230–1470.

## 4. Motion language

- **Easing:** a single deceleration curve, `cubic-bezier(0.16, 1, 0.3, 1)`, for all entrances. Exits are shorter and linear. No bounces.
- **Reveals:** text enters as a masked line reveal (clip-path), 450 ms. Numerals count up for 500 ms.
- **Mechanical echoes:** reuse one gesture — a tick-mark wipe — across labels, the legend chips and the end card, so the 2D feels machined like the 3D.
- **Restraint:** no more than one text element animating at a time; no particle confetti; no generic template cards.

## 5. Scenes in Remotion

All text below is a **proposal derived from the supplied narration** and needs approval; none adds a claim beyond `research/fact-check.md`.

| Scene | 2D content | Detail |
|---|---|---|
| 01 | Two text lines | "MORE THAN 2,000 YEARS AGO…" (frame 0), "A MACHINE TO PREDICT THE SKY." (frame 117) |
| 02 | Two diagrams + labels | D1 Sun and Moon (frames 267–351, label "SUN · MOON" at 270), D3 eclipse-cycle schematic (351–423, label "ECLIPSE PREDICTION CYCLE"); micro-label "SIMPLIFIED ILLUSTRATION" throughout |
| 03 | Locator + label | "ANTIKYTHERA, GREECE — 1901" at frame 465; permanent **DRAMATIZED RECONSTRUCTION** label from 423 to 650 |
| 04 | Count-ups | "82 SURVIVING FRAGMENTS" at frame 651, "30 SURVIVING GEARS" at 704; leader lines locked to Blender anchors; optional D4 ring at 810 (needs approval) |
| 05 | Legend | "SURVIVING EVIDENCE · RECONSTRUCTION" chips at frame 930 |
| 06 | Title, subtitle, scientific term, brand | See §8 |

## 6. Blender → Remotion anchors

To keep labels attached to real parts of the 3D shot, Blender exports a JSON of **screen-space anchor positions per frame** (empties projected through the shot camera). Remotion reads it with `staticFile()` and draws leader lines to those points. Needed anchors: `fragments_centre`, `gear_group`, `pointer_tip`, `moon_dial_centre`, `case_corner`. The Blender side is specified in `design/blender-art-direction.md` §8.

## 7. Scientific diagrams (scene 02)

All are **simplified illustrations** and carry the micro-label **SIMPLIFIED ILLUSTRATION**. They are not footage of the original machine working.

| ID | Diagram | What it teaches | Build | Status |
|---|---|---|---|---|
| D1 | **Sun and Moon cycle** | The Moon completes its phase cycle faster than the Sun advances through the year | Two concentric rings with pointers; the Moon pointer shows a phase glyph updating; period labels only if verified (C12) | Used (scene 02) |
| D3 | **Eclipse-cycle schematic** | A repeating cycle in which eclipses recur (the Saros cycle) | A ring timeline with 2–3 eclipse glyphs lighting up; an Earth–Moon–Sun alignment inset. **Print 223 / 235 / "18 years 11 days" only after C12 is verified** | Used (scene 02) |
| D4 | **"About one third survives" ring** | How much of the original remains | A progress ring at ≈ 33%, label "ABOUT ONE THIRD SURVIVES" (C08) | Optional (scene 04); not in the script, needs approval |
| D2 | Calendar dial | A circular calendar read by a pointer | — | **Unused**: calendars are not narrated in script v2 |

Use the installed `remotion-markup` skills for timing, sequencing, `measuring-text`, `text-highlights` and `transitions`.

## 8. Scenes 05 and 06: legend, title, scientific term, brand

| Time | Element | Behaviour |
|---|---|---|
| 31.0 s (frame 930) | Scene 05 legend: **SURVIVING EVIDENCE · RECONSTRUCTION** | Two chips; the second in Scientific Cyan. Tied to the ghosting in the 3D plate |
| 39.1 s (frame 1173) | **THE ANTIKYTHERA MECHANISM** | Three lines (THE / ANTIKYTHERA / MECHANISM), Warm Ivory on a Midnight Navy scrim, tick-mark wipe |
| 41.2 s (frame 1236) | **THE OLDEST KNOWN ANALOGUE COMPUTER** | The popular label. Appears *as* "oldest known" is spoken, not before |
| 43.2 s (frame 1296) | **SCIENTIFIC TERM: MECHANICAL CALCULATOR** | The careful term, directly under the subtitle in IBM Plex Mono, Scientific Cyan, about half the subtitle size. Held about 2.8 s (to frame 1380). Studio decision: popular label first, scientific term explained on screen |
| 46.0 s (frame 1380) | **EPOCH & ELEMENT** + **The Forces That Shaped Our World.** | The mark animates in over 24 frames and holds to frame 1440 |

**Layout (scene 06):** title block y ≈ 360–780; subtitle y ≈ 800–900; scientific-term line y ≈ 930–990; brand mark y ≈ 1040–1180; captions y ≈ 1230–1470.

The brand mark and logo lockup do not exist in the repository. **No logo artwork has been created or invented**; the end card uses the wordmark in Space Grotesk until the studio supplies a mark (the Bible's `Brand_Assets/` folder holds none yet).

## 9. Captions

Source: `captions/subtitles.srt`, parsed with `parseSrt()` from `@remotion/captions` (see the installed `remotion-captions` skill: `import-srt-captions.md`, `display-captions.md`).

| Property | Value |
|---|---|
| Position | Centre-aligned, y ≈ 1230–1470, above the Shorts UI zone |
| Size | 54–62 px, Inter 600, Warm Ivory |
| Lines | Max 2 lines, max 28 characters per line (the SRT is already chunked this way) |
| Background | None. Use a soft text shadow plus a subtle bottom gradient scrim (navy at about 55% to 0%); no cards |
| Emphasis | The stressed word in `--gold` (Antique Gold), matching the emphasis column in `script/voiceover-en.md` |
| Entry / exit | 6-frame fade; no per-word bounce |
| Conflicts | A caption never overlaps a data label; if one does, the label moves up or the caption chunk is split |

Burn the captions into the video (for sound-off viewing) **and** upload the `.srt` to YouTube. Non-speech sound captions are optional; see `audio/audio-direction.md` §5.

## 10. Transitions (3D ↔ 2D)

| Transition | Method |
|---|---|
| 01 → 02 | Continuous: the pull-back lands on the dial plate where the diagrams begin |
| Diagram ↔ plate (02) | The diagram ring "resolves" out of the dial in the plate: a circular mask grows from the pointer tip |
| 02 → 03 | Hard cut; a 6-frame navy-to-teal colour wash on the text layer |
| 03 → 04 | Warm light sweep from the top; labels enter after the sweep |
| 04 → 05 → 06 | Continuous; the ghost layer resolves as the final orbit begins |
| End | The brand mark appears with the tick-mark wipe; no extra effect |

## 11. Implementation notes

- **Skills to use:** `remotion-create`, `remotion-markup`, `remotion-interactivity` (keep markup editable in Studio), `remotion-captions`, `remotion-studio`, `remotion-render`. Others in the collection (`remotion-maps`, `remotion-saas`, `remotion-elements`, `remotion-multimedia`) are not needed for Shorts 001.
- **Dependencies not yet installed:** the Remotion packages (`remotion`, `@remotion/cli`, `@remotion/captions`, fonts). Installing them is an `npm install`, a network step performed in the next phase.
- **Available in this environment:** Node 22.23.5, npm 10.9.9, ffmpeg/ffprobe 6.1.1. Remotion also downloads a headless Chrome for rendering.
- **Licence:** Remotion's own licence applies to commercial company use. The installed `remotion-license` skill describes it; the team should confirm which terms apply before the channel is monetised. This document makes no claim either way.
- **Testing before final render:** preview in Remotion Studio, scrub every scene boundary, render a single still per scene and review at phone size, then a low-resolution preview render. **No final render in pre-production.**
