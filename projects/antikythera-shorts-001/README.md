# EPOCH & ELEMENT — S001: The 2,000-Year-Old Computer

*The Forces That Shaped Our World.*

| | |
|---|---|
| Project ID | S001 (Shorts 001) |
| Subject | The Antikythera Mechanism |
| Alternate title (Bible) | The Machine That Predicted Eclipses |
| Format | YouTube Short · 9:16 · 1080 × 1920 · 30 fps |
| Script | **v2, supplied by the studio, used word for word** (102 words) |
| Duration | Nominal **48.0 s (1,440 frames)**; studio tolerance up to **55 s (1,650 frames)** |
| Look | Production Bible §4–§6: cinematic stylised realism, Blender 3D + 2D motion graphics |
| Phase | **Pre-production. No production work has started.** |

**Source of truth:** `00_STUDIO/Production_Bible.md` (v0.1, an unmodified copy of the studio's upload).

## 1. The script

The narration in `script/voiceover-en.md` is exactly the text the studio supplied. **Nothing was reworded, reordered or trimmed.** Checked line by line against the research (`research/fact-check.md`, "Script v2, line by line"): **no factual error**. Two optional observations are listed in `voiceover-en.md` §3 and are **not applied**:

1. "**Found** in a shipwreck… in 1901": the wreck was found in 1900 and the mechanism recovered in 1901 (alternative: "Recovered from…").
2. "Often called the world’s oldest known analogue computer": fine as written; the scientific term appears on screen.

The earlier working script (v1.1) and its derived files are kept in the `archive/` folders. Nothing was deleted.

**Timing (a model, not a measurement; no voice recorded):** narration ends at **46.7 s** at 150 wpm (45.4–48.1 s across 155–145 wpm). With a 1.3 s tail the video is about **48 s**, over the old 45 s target and inside your 55 s tolerance with more than 5 s to spare.

## 2. Status

| Area | Status | Notes |
|---|---|---|
| Research brief (Bible §8.4) | Done | `research/research-brief.md` |
| Fact-check | **Done, with gaps** | 23 claims. Two Nature papers read as abstracts only; the UCL release **not read** (HTTP 403) |
| Script v2 | **Verbatim, fact-checked** | See §1 |
| Indonesian reference | Done | Follows script v2 |
| Storyboard + shot list | **Proposed, needs approval** | 6 scenes, 15 shots summing to 48.0 s. Rebuilt for the new narration order |
| On-screen text | **Proposed, needs approval** | `production/quality-control.md` register. Not in the script, so none is final |
| Blender / Remotion art direction | Done | Spec only. **Blender is not installed here**; no model, no render |
| Subtitles | **Draft** | `captions/subtitles.srt`, 18 cues, model-timed; retime from the real take |
| Sound | **Deferred to the studio** | `audio/audio-direction.md` is a method and mix plan; its cue sheet is **stale** (timed to v1.1) |
| Asset manifest (Bible §10.3) | Done | 45 assets, none produced |
| QC, YouTube package, skills audit | Done / draft | |
| **Renders / tests / validation** | **None run** | By design |

## 3. Decisions recorded

- **Terminology (studio):** "analogue computer" is the popular label; the scientific term "mechanical calculator" is stated on screen in scene 06 (41.2 s subtitle, 43.2 s scientific-term line). The new narration already hedges with "Often called…".
- **Duration:** up to 55 s is acceptable; the hard cap is 1,650 frames.
- **Sound:** the studio will handle it later.

## 4. Decisions still needed

1. **Confirm the on-screen text and storyboard** (the proposals above), including whether to keep the **SCIENTIFIC TERM: MECHANICAL CALCULATOR** line, which is not in the narration.
2. **Line 3 wording** ("Found" vs "Recovered"): leave as is, or change it?
3. **Narrator** (when sound starts): human or licensed synthetic voice.
4. **Remotion licence:** which terms apply to this channel.
5. **Folder layout:** the Bible suggests a studio working tree; the brief asked for `projects/antikythera-shorts-001/`. Documents live here; the manifest's `file_path` column uses the Bible's tree for future binary assets. Say if you want the documents migrated.
6. **Brand mark:** none exists; the end card uses a wordmark until you supply one.
7. **Scene order:** the Bible's skeleton is wreck-first; the supplied script is capability-first, and the storyboard follows the script.

## 5. Blockers and caveats

- **UCL 2021 source:** blocked (403 on three attempts). Nothing relies on it.
- **Full Nature texts:** not accessible, so gear tooth counts and the crank evidence are unverified. **No gear data appears anywhere in this package.**
- **Calendars and the hand crank** are no longer in the narration. The calendar-dial diagram is marked *Unused*; the crank model is optional.
- **Blender:** missing here, and there is no GPU; final Cycles rendering needs a GPU machine. Audacity (Bible §15) is also not installed; FFmpeg is.

## 6. Files

| File | Purpose |
|---|---|
| `README.md` | This overview |
| `research/research-brief.md` | Bible §8.4 research brief |
| `research/fact-check.md` | Script v2 line-by-line check + 23 claims with evidence, source, confidence, phrasing |
| `research/sources.md` | Source register with what was actually retrieved |
| `script/voiceover-en.md` | The supplied narration (verbatim), suggestions not applied, timing, delivery |
| `script/translation-id.md` | Indonesian reference translation (script v2) |
| `storyboard/storyboard.md` | Scene-by-scene storyboard for script v2 (proposed) |
| `storyboard/shot-list.csv` | 15 shots with narration, camera, graphics, transition and assets (Bible §9 stage 4) |
| `design/blender-art-direction.md` | Hero asset, modelling, materials, lighting, cameras, rendering |
| `design/remotion-art-direction.md` | Compositions, Bible colours and type, diagrams, captions, transitions |
| `audio/audio-direction.md` | Method and mix plan (cue sheet stale; studio handles sound later) |
| `captions/subtitles.srt` | English subtitles for script v2 (18 cues, model-timed) |
| `production/asset-manifest.csv` | 45 assets, Bible fields and `EE_S001_…_v##` naming |
| `production/quality-control.md` | Factual, visual, audio, technical, publishing gates + Bible §12 crosswalk |
| `production/skills-audit.md` | Installed skills, find-skills results, decisions, dependencies |
| `publishing/youtube-package.md` | Titles, description, hashtags, cover frame, pinned comment |
| `*/archive/` | Superseded v1.1 script, translation, SRT, storyboard and shot list |

Outside this folder: `00_STUDIO/Production_Bible.md` and `.claude/skills/sound-design-foley/`.

## 7. Recommended next step

1. You approve (or adjust) the **storyboard and on-screen text**, and decide on **line 3**. Per the Bible (§11.2, rule 4), no production code starts before that.
2. Retrieve the **full texts** (Nature 2006, SR21 supplementary data) and the UCL page; fill the gear-data table.
3. Install headless Blender on a GPU-capable machine and run the **gear-generator smoke test**.
4. When sound starts: record the voice-over, then regenerate the SRT and scene frames from the real take.
