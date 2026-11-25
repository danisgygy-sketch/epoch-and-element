# Quality Control — Shorts 001

Every box below is a **gate**. Nothing has been checked yet except where marked. A box is ticked only when someone has actually looked or measured, with the result noted. Items marked **(blocking)** must pass before publishing.

## 0. What has been verified so far (pre-production)

| Check | Result |
|---|---|
| 14 official Remotion skills installed with valid `SKILL.md` | Verified (file check) |
| `sound-design-foley` installed, no duplicate skill names | Verified |
| SRT file generated from the narration model | Generated; **timings are model-based, not measured** |
| UCL 2021 source read | **No.** HTTP 403 |
| Nature 2006 and Nature Astronomy 2018 read in full | **No.** Abstracts only |
| Blender available | **No.** Not installed here |
| Production Bible read and applied (palette, fonts, manifest, brief format, QC) | Yes, after it was supplied |
| Script v2 checked line by line against the fact-check | Yes: no factual error; one low-severity wording flag (line 3) |
| Any render, test or validation run | **None.** Pre-production only |

## 1. Factual QC (blocking)

- [ ] Every spoken line maps to a `research/fact-check.md` row marked Established or Strongly supported.
- [ ] Every on-screen text appears in the register below with a fact-check ID.
- [ ] No claim from the "never make" list in `fact-check.md` appears anywhere (voice, captions, labels, description, comment).
- [ ] "Probably" survives in the date line; no single construction year.
- [ ] "82 surviving fragments" and "30 surviving gears" are the only counts shown. No 35 / 37 / 69.
- [ ] Open verification items 1–5 in `fact-check.md` are closed, or the affected graphic is removed.
- [ ] If numbers 223 / 235 / "18 years 11 days" appear, C12 is verified against a full text.
- [ ] The UCL release has been read before it is cited anywhere.

### On-screen text register

All text is a **proposal derived from the supplied narration** (which is unchanged). Anything not literally in the script needs approval.

| Text | Scene / time | Fact-check ID | Status |
|---|---|---|---|
| MORE THAN 2,000 YEARS AGO… | 01 / 0.0 s | C01 (line 1) | proposed |
| A MACHINE TO PREDICT THE SKY. | 01 / 3.9 s | line 1 | proposed |
| SUN · MOON | 02 / 9.0 s | C10 | proposed |
| ECLIPSE PREDICTION CYCLE | 02 / 11.7 s | C11 | proposed |
| SIMPLIFIED ILLUSTRATION | 02 | policy | **required** |
| ANTIKYTHERA, GREECE — 1901 | 03 / 15.5 s | C03, C05 (flag: the wreck was found in 1900) | proposed |
| DRAMATIZED RECONSTRUCTION | 03 | policy | **required** |
| 82 SURVIVING FRAGMENTS | 04 / 21.7 s | C06 (spoken in the script) | proposed |
| 30 SURVIVING GEARS | 04 / 23.45 s | C07 (spoken in the script) | proposed |
| ABOUT ONE THIRD SURVIVES | 04 / 27 s | C08 | optional; needs approval |
| SURVIVING EVIDENCE · RECONSTRUCTION | 05 / 31.0 s | evidence tiers | **required** |
| THE ANTIKYTHERA MECHANISM | 06 / 39.1 s | — | proposed |
| THE OLDEST KNOWN ANALOGUE COMPUTER | 06 / 41.2 s | C16 (matches the narration) | proposed |
| SCIENTIFIC TERM: MECHANICAL CALCULATOR | 06 / 43.2 s | C16 | **required** by the studio decision; please confirm |
| EPOCH & ELEMENT + tagline | 06 / 46.0 s | — | proposed |

## 2. Visual QC

- [ ] Evidence tiers are respected: Tier C is always ghosted; Tier B is clean; Tier A shows damage.
- [ ] No decorative gears without a mechanical purpose; every visible gear belongs to the gear table.
- [ ] No invented Greek text.
- [ ] Gear meshing passes the 12-angle collision check (`blender-asset-qa`).
- [ ] Bronze is not plastic, chrome or over-saturated gold; highlights are not clipped; no excessive bloom.
- [ ] Depth of field keeps the teaching element in focus on every shot.
- [ ] Consistent colour grade across all shots (compare a contact sheet).
- [ ] Text contrast ≥ 4.5 : 1 on the real frames.
- [ ] Safe areas respected: nothing important in the bottom 440 px or the right 120 px.
- [ ] Mobile review: viewed at phone size, captions readable at arm's length.
- [ ] Scene 03 carries the DRAMATIZED RECONSTRUCTION label and does not look like archival footage.
- [ ] The end card does not use invented logo art.

## 3. Audio QC

- [ ] Narration is intelligible over music and effects on phone speakers and headphones.
- [ ] Consistent pronunciation of "Antikythera".
- [ ] Frame-locked cues (first gear tick, underwater cut, title impact) are within ±2 frames.
- [ ] Integrated loudness and true peak measured and recorded (working target about −14 LUFS, true peak ≤ −1 dBTP; confirm against current platform guidance).
- [ ] No clipping, no harsh high-frequency spikes, no excessive sub-bass.
- [ ] Every audio asset has a recorded licence that permits commercial, monetised use.
- [ ] Music is never louder than the voice while speaking.

## 4. Caption QC

- [ ] SRT matches the final narration exactly, with no stale lines from an earlier script.
- [ ] Max 2 lines and 28 characters per line.
- [ ] Caption times are regenerated from the real VO take (the current SRT is model-based).
- [ ] The burned-in captions and the uploaded SRT match.

## 5. Technical QC (blocking)

- [ ] 1080 × 1920, 30 fps, 9:16, within the studio's 55 s tolerance (≤ 1,650 frames; nominal 1,440).
- [ ] Re-time check: scene frames in `design/remotion-art-direction.md` match the real take.
- [ ] No dropped or duplicated frames; audio and video in sync at start, middle and end.
- [ ] Fonts loaded before render; no fallback font visible.
- [ ] A still from each scene was reviewed before the final render.
- [ ] Final file plays on a phone.
- [ ] Remotion licence terms confirmed for this channel's use.

## 6. Publishing QC (blocking)

- [ ] Title and cover frame are not misleading (see `publishing/youtube-package.md`).
- [ ] The description states that visuals are artistic reconstructions and that the device is a mechanical analogue calculator, not a digital computer.
- [ ] Source list contains only sources actually read.
- [ ] Hashtags are relevant; no unrelated tags.
- [ ] Altered or synthetic content disclosure is considered if any realistic synthetic voice or footage is used, per the platform's current policy.

## 6b. Production Bible §12 crosswalk

The Bible's checklists are the studio standard. Items already covered above are not repeated; these are the ones this file added from the Bible.

**Research (§12.1)**
- [ ] Names, dates, numbers and terms checked against the research brief.
- [ ] Reconstructions are not presented as certain historical footage.

**Script (§12.2)**
- [ ] The hook matches the video's content.
- [ ] The main question ("How could people build this 2,000 years ago?") is answered, or its limits stated.
- [ ] The narration is easy to follow when heard (read it aloud once).
- [ ] No unnecessary repetition; duration within target.
- [ ] English proofread.

**Visual (§12.3)**
- [ ] The focus of each scene is clear within a moment.
- [ ] Models and materials are consistent across scenes.
- [ ] Lighting supports form and mood.
- [ ] Animation never obscures understanding.
- [ ] No wrong object, label or transition.

**Export (§12.5)**
- [ ] No black frames or broken render frames.
- [ ] Subtitles and text are not clipped.
- [ ] Final file and project files saved with Bible §10.2 names (`EE_S001_…_v##`).

## 7. Sign-off

| Role | Name | Date | Result |
|---|---|---|---|
| Research / fact-check | | | |
| Visual (Blender) | | | |
| Motion graphics (Remotion) | | | |
| Audio | | | |
| Publishing | | | |
