# Storyboard — The 2,000-Year-Old Computer

Format 9:16 · 1080 × 1920 · 30 fps · hard cap **1,350 frames (45.0 s)**.
Timings are retimed from the original 6-scene plan to the narration model in `script/voiceover-en.md` (150 wpm). They will shift once a real voice take exists.

**Division of labour:** **B** = rendered in Blender (3D). **R** = built in Remotion (2D). Every scene shows which tier of evidence it depicts (A surviving / B inferred / C hypothesis / D dramatised, see `research/fact-check.md`).

## Overview

| # | Scene | Time | Frames | Narration | Main medium | Evidence tier |
|---|---|---|---|---|---|---|
| 01 | The Hook | 0.0–4.6 | 0–138 | "Two thousand years ago… bronze gears." | B + R | B (inferred, artistic) |
| 02 | Not a Modern Computer | 4.6–11.3 | 138–339 | "No electricity… model the sky." | B + R | B |
| 03 | Discovery | 11.3–16.4 | 339–492 | "Recovered from a shipwreck… in 1901," | B + R | **D (dramatised)** |
| 04 | The Mechanism Revealed | 16.4–21.8 | 492–654 | "its corroded fragments… 150 and 100 BCE." | B + R | A → B |
| 05 | Calculating the Sky | 21.8–29.7 | 654–891 | "Turn the crank… predict eclipses." | R-led + B | B (+ simplified diagram) |
| 06 | Final Reveal | 29.7–45.0 | 891–1350 | "It is known as… could be." | B + R | A / B / C legend |

## Global rules

- **Vertical composition.** Important content sits in the centre 1080 × 1200 px band. Reserve the bottom 440 px for YouTube's Shorts interface (title, channel, buttons) and 120 px on the right for its icons. Captions live at y ≈ 1230–1470.
- **One idea per shot.** Every shot answers a question on the audience's mind at that moment.
- **No archival look.** Scene 03 and any diver or wreck imagery carry a persistent small label **DRAMATIZED RECONSTRUCTION**. Never film-grain it into pseudo-archive footage.
- **Evidence legend.** Whenever Tier C (hypothesis) geometry is on screen, it is ghosted and labelled (see scene 06).
- **Motion language.** Slow, deliberate camera. Gears turn at one constant, believable speed; the crank drives everything (single driver, see `design/blender-art-direction.md` §6).
- **Edit rhythm.** Cut on the narration's sentence breaks; hold macro shots for at least 1.2 s; no shot longer than 6 s.

---

## Scene 01 — The Hook · 0.0–4.6 s · frames 0–138

**Narration:** "Two thousand years ago, someone built a computer from bronze gears."

| Beat | Time | Shot |
|---|---|---|
| 1a | 0.0–1.7 | **B.** Black. A low raking light picks out one bronze gear in extreme macro (85 mm, shallow DOF). The gear begins to turn, slowly, teeth catching light. |
| 1b | 1.7–3.4 | **B.** A second gear enters frame and **engages**; the tooth contact is precise and visible. Camera pushes in 4%. |
| 1c | 3.4–4.6 | **B.** Rack focus to a third gear in the background. Dust motes in a narrow volumetric beam. |

**On-screen text (R):**
- 0.0 s: **2,000 YEARS AGO…** — small, wide-tracked, upper third, fades up with the first words.
- 1.7 s: **A COMPUTER WAS ALREADY POSSIBLE.** — slightly larger; words arrive on the narration's stress (computer / bronze).

**Sound:** very low ambience; one soft bronze "tick" on gear engagement (frame-locked at 1.7 s); no music hit yet.
**Feeling:** mysterious, intelligent, cinematic.
**Fact-check:** C16 ("computer" is figurative here; the description clarifies "mechanical analogue calculator"). The "already possible" line is editorial, not a historical claim.

---

## Scene 02 — Not a Modern Computer · 4.6–11.3 s · frames 138–339

**Narration:** "No electricity. No screen. Just a hand-crank—and a machine designed to model the sky."

| Beat | Time | Shot |
|---|---|---|
| 2a | 4.6–6.3 | **B.** Camera glides *through* the rotating gears (a slow tracking move inside the mechanism). Foreground gears are soft; the focus plane slides past them. |
| 2b | 6.3–8.2 | **B.** The camera finds a plain **hand crank** and rotates with it: the one human input driving every gear behind. |
| 2c | 8.2–11.3 | **B.** Pull back and up to show the whole gear train turning from the single crank. The dials come into frame, still unreadable. |

**On-screen text (R):** **NO ELECTRICITY.** at 4.62 s and **NO SCREEN.** at 6.34 s, each as a single line locked to the word, 450 ms in, fading out as the next arrives.
**Sound:** a mechanical clicking bed gradually appears as the camera enters the mechanism; a low drone underneath.
**Fact-check:** C15. The crank is a reconstruction, so it uses the Tier B treatment (clean matte, no patina).

---

## Scene 03 — Discovery · 11.3–16.4 s · frames 339–492

**Narration:** "Recovered from a shipwreck near the Greek island of Antikythera in 1901,"

| Beat | Time | Shot |
|---|---|---|
| 3a | 11.3–13.4 | **B.** Hard cut to **underwater**: a cold teal-blue column of light from the surface, drifting particles, a sandy seabed with amphora shards and timber ribs. Slow lateral dolly. |
| 3b | 13.4–15.0 | **B.** Close on a **corroded bronze lump** half-buried among debris; sediment lifts as a hand-less "lifting" move (the camera rises with it) suggests recovery. |
| 3c | 15.0–16.4 | **B → R.** The lump rises into the light; the screen warms from teal to bronze as the surface approaches. |

**On-screen text (R):** **ANTIKYTHERA, GREECE — 1901** from 14.4 s (on "of Antikythera in 1901"), set as a small map-style locator. A permanent micro-label bottom-left: **DRAMATIZED RECONSTRUCTION**.
**Sound:** hard transition from the gear bed to muffled underwater ambience (low rumble, faint bubbles); silence of metal; one dull thud as the lump lifts.
**Fact-check:** C03, C05. Say 1901 only. No month. This is a **dramatisation**, not archival footage, and it does not depict the real fragments.

---

## Scene 04 — The Mechanism Revealed · 16.4–21.8 s · frames 492–654

**Narration:** "…its corroded fragments concealed a device probably built between 150 and 100 BCE."

| Beat | Time | Shot |
|---|---|---|
| 4a | 16.4–18.4 | **B.** Macro of a **corroded fragment** with exposed gear teeth under crust; fine surface detail, cracked patina, no clean bronze. (Tier A treatment) |
| 4b | 18.4–20.4 | **B.** The fragments slide apart into an **exploded view**; hidden gears resolve as the crust "fades" in a controlled material blend, gears in clean bronze, spaced in layers. |
| 4c | 20.4–21.8 | **B.** The exploded stack settles into the assembled mechanism; the crank socket and pointers visible. |

**On-screen text (R):**
- 18.9 s: **82 SURVIVING FRAGMENTS** (count-up 0→82, 0.5 s).
- 19.5 s: **30 SURVIVING GEARS** (count-up 0→30).
- 20.4 s: **c. 150–100 BCE** as a slim timeline label, with the word "probably" in the narration carrying the hedge. Leader lines are anchored to Blender's projected points (see Remotion spec §6).

**Sound:** rising low tone; crisp metallic "slide" on the explode; a soft impact as the stack settles.
**Fact-check:** C01, C06, C07. Use only the figures in this table. **Do not** show 35, 37 or 69.

---

## Scene 05 — Calculating the Sky · 21.8–29.7 s · frames 654–891

**Narration:** "Turn the crank, and its dials could track the cycles of the Sun and Moon, follow complex calendars, and predict eclipses."

| Beat | Time | Shot |
|---|---|---|
| 5a | 21.8–23.8 | **B.** A hand turns the crank **(rendered as a stylised, faceless hand, or crank-only if the hand is not ready)**. The gears answer; a pointer begins to move. |
| 5b | 23.8–26.0 | **R over B.** A **Sun-and-Moon diagram** resolves beside the macro: the Moon pointer circles a ring while the Sun pointer advances slowly; the phase of the Moon updates. |
| 5c | 26.0–27.8 | **R.** A **calendar dial** appears; a pointer sweeps month names, then freezes on a lined-up month. |
| 5d | 27.8–29.7 | **R.** A **simplified eclipse-cycle illustration**: an Earth–Moon–Sun alignment in a clean 2D schematic with an eclipse glyph appearing on the dial's cycle. Caption: **ECLIPSE PREDICTION CYCLE**. |

**On-screen text (R):** the three diagrams are the content. Minimal labels: **SUN · MOON**, **CALENDAR**, **ECLIPSES**; no sentences.
**Sound:** the click bed becomes more rhythmic; soft "tick" on each diagram reveal; a gentle chime on the eclipse glyph.
**Fact-check:** C10, C11, C12 (**VERIFY** before printing 223 / 235). All diagrams are **explanatory schematics**, not footage of the original running. They carry the small label **SIMPLIFIED ILLUSTRATION**.

---

## Scene 06 — Final Reveal · 29.7–45.0 s · frames 891–1350

**Narration:** "It is known as the Antikythera Mechanism—the oldest known analogue computer. Its complete design remains debated. But the surviving machine shows how sophisticated ancient Greek engineering could be."

| Beat | Time | Shot |
|---|---|---|
| 6a | 29.7–36.4 | **B.** Slow, low orbit around the **completed artistic reconstruction in its case**: warm bronze highlights against dark navy. The title lands on the narration of the name. |
| 6b | 36.4–42.0 | **B + R.** On "Its complete design remains debated": some gears **ghost out** into translucent Scientific Cyan wireframes (Tier C) while the surviving core stays solid bronze. A two-chip legend appears: **SURVIVING EVIDENCE · RECONSTRUCTION**. |
| 6c | 42.0–45.0 | **B.** The ghosting resolves; the camera finishes its pull-back to a calm wide of the mechanism. The EPOCH & ELEMENT brand mark fades in over the last 2.5 s as the final words finish. |

**On-screen text (R):**
- 29.85 s: title **THE ANTIKYTHERA MECHANISM** (three lines, large).
- 33.24 s: subtitle **THE OLDEST KNOWN ANALOGUE COMPUTER** (the popular label, after the narration says it).
- 34.6 s: **SCIENTIFIC TERM: MECHANICAL CALCULATOR** in smaller type directly beneath (the careful term; studio decision: popular hook first, scientific term explained on screen, no extra narration time).
- 36.4 s: legend chips (small).
- 42.5 s: **EPOCH & ELEMENT** brand mark + tagline **The Forces That Shaped Our World.** (held 2.5 s).

**Sound:** the first restrained cinematic impact at the title (low, short); music resolves into a warm sustained tone; the click bed fades to near-silence by 44 s.
**Fact-check:** C14, C16, C21. The subtitle keeps the "oldest known" hedge; **do not** shorten it to "first computer". The scientific-term line is required, not optional.

---

## Shot list (for Blender)

| Shot | Scene | Camera | Length | Hero? |
|---|---|---|---|---|
| S01-A | 01 | Macro 85 mm, locked + slow push | 1.7 s | gear pair |
| S01-B | 01 | Macro, rack focus | 2.9 s | gear train |
| S02-A | 02 | 50 mm, tracking through mechanism | 1.7 s | hero |
| S02-B | 02 | 85 mm, orbiting crank | 1.9 s | crank |
| S02-C | 02 | 35 mm, pull-back reveal | 3.1 s | hero |
| S03-A | 03 | 35 mm, underwater lateral dolly | 2.1 s | environment |
| S03-B | 03 | 50 mm, rising with the lump | 3.0 s | corroded lump |
| S04-A | 04 | Macro 100 mm, corroded fragment | 2.0 s | fragment set |
| S04-B | 04 | 50 mm, exploded view | 2.0 s | hero (exploded) |
| S04-C | 04 | 50 mm, settle | 1.4 s | hero |
| S05-A | 05 | 85 mm, crank + pointer | 2.0 s | hero + crank |
| S05-BG | 05 | plate for diagrams | 5.9 s | back dial (soft) |
| S06-A | 06 | 50 mm, orbit, low | 6.7 s | hero in case |
| S06-B | 06 | 50 mm, same orbit + ghosting | 5.6 s | hero (tiered materials) |
| S06-C | 06 | 35 mm, pull-back | 3.0 s | hero + brand plate |

Shot lengths sum to exactly 45.0 s; the same list, with narration, camera, motion graphics, transitions and assets per shot, is in `shot-list.csv` (Bible §9 stage 4).

## Transitions (summary)

| Cut | Type | Notes |
|---|---|---|
| 01 → 02 | Continuous camera move | No cut; the push continues through the gears |
| 02 → 03 | **Hard cut to teal** | The only hard cut; reinforced by the audio shift |
| 03 → 04 | Warm dissolve on the lifting lump | Bronze light from the surface |
| 04 → 05 | Match on the settled mechanism | Pointer starts moving at the cut |
| 05 → 06 | Diagram dissolves into the macro | Camera begins the orbit |

## Alignment with the Production Bible

The Bible's starting skeleton (§14.4) is a framework that "research and the final script must decide". This storyboard follows the brief's six scenes and covers every Bible beat:

| Bible beat (§14.4) | Where it lives here |
|---|---|
| 01 The Wreck | Scene 03 (Discovery), after the hook establishes the object |
| 02 The Artifact | Scene 04a (corroded fragment close-up) |
| 03 The Gears | Scenes 01, 02 and 04b (macro gears, exploded view) |
| 04 The Cycles | Scene 05 (Sun, Moon and calendar diagrams) |
| 05 The Eclipse | Scene 05d (eclipse-cycle schematic) |
| 06 The Hero Shot | Scene 06 (final reveal with studio identity) |

The order differs on purpose: the hook shows the *object first* (a Shorts retention choice), then the wreck. If you prefer the Bible's wreck-first order, only scenes 01–04 need re-sequencing; the narration would have to be reordered too, so it is a decision for the script owner.

Bible §9 stage 4 requires, per scene: duration, narration, main visual, camera movement, object movement, motion graphics, transition and assets needed. These are in `shot-list.csv`, whose asset names match `production/asset-manifest.csv`.
