# Audio Direction — Shorts 001

> **STALE — retime before use.** The cue sheet below was timed to script v1.1 (45 s). The studio supplied a new script (v2, nominal 48.0 s), and the studio will handle sound later. Treat this file as a *method and mix plan*; redo the cue-sheet times from `script/voiceover-en.md` §5 and `storyboard/shot-list.csv` when audio work starts.

Prepared with the installed `sound-design-foley` skill (its spotting-first method: decide what the audience must feel and notice, then place sound only where it clarifies cause, timing or emotion).

**Status:** plan only. No audio was recorded, synthesised or sourced. Frame times come from the narration model (150 wpm); retime after the real take.

## 1. Mix priorities

1. **Voice-over** — always foreground and intelligible.
2. **Key mechanical sounds** — frame-locked gear engagement, crank, reveals.
3. **Ambience** — underwater and room tone, supporting.
4. **Music** — a bed that never competes with the narrator.

Principle from the skill: don't fill every frame. Too many literal sounds fight the voice. Silence and a clean click carry more than layers.

## 2. Voice-over

| Item | Spec |
|---|---|
| Language / tone | International English, calm documentary tone; not theatrical (see `script/voiceover-en.md` §5) |
| Recording | Human narrator preferred. Mono, 48 kHz, 24-bit WAV, quiet treated room, pop filter, no processing on delivery |
| If TTS is used instead | The vendor and voice are an **open decision** (see README). The script and project data would be sent to that service. Choose a service whose licence permits commercial use and monetised YouTube publication, and keep the licence in `production/asset-manifest.csv` |
| Pace | 150–155 wpm |
| Pronunciation | Pick **one** pronunciation of "Antikythera" and use it consistently; "BCE" as letters |
| Takes | Record the full read twice, plus pick-ups for the hook and the final line |
| Delivery | One dry WAV per take; the VO file is the **timing source of truth** |

## 3. Sound effects

| Layer | Content | Source plan |
|---|---|---|
| Gear mesh | Soft bronze ticks, tooth-to-tooth, rhythmic; pitch drifts slightly with speed | Record or synthesise; do not use cartoon "clockwork" loops |
| Crank | A turning handle with a faint ratchet | Record/synthesise |
| Underwater | Low rumble, bubbles, distant creak | Record/synthesise; or CC0 library with a verified licence |
| Reveals and transitions | Soft metallic slide on the exploded view; a gentle shimmer on diagram reveals | Synthesise |
| Impacts | One restrained low impact at the title; one dull thud on the lump | Synthesise |
| Diagram "ticks" | Tiny UI-like ticks for count-ups, deliberately dry and short | Synthesise |

**Rights rule** (from the installed skill): every sound is either recorded or synthesised in-house, or comes from a library whose licence permits commercial, monetised use. Creative Commons terms vary per asset (attribution, non-commercial limits), so check each file. The YouTube Audio Library is described in the skill as copyright-safe for YouTube use, but its own terms should be checked at the time of use. Track everything in `production/asset-manifest.csv`.

## 4. Music

| Item | Spec |
|---|---|
| Role | A quiet bed that adds mystery, then warmth |
| Instrumentation | Low sustained drone; sparse plucked strings with a lyre-like timbre (suggestion, not a claim of authenticity); soft pulse; no drums; no heroic brass |
| Level | Always at least 12–15 dB below the voice while speaking |
| Source | **Original composition** or properly licensed library music with commercial/monetisation rights, licence stored in the manifest. No track has been chosen |

**Arc by scene**

| Scene | Music |
|---|---|
| 01 | Near-silence; a single low pulse starts at 1.7 s |
| 02 | Pulse becomes a slow ostinato; drone enters |
| 03 | Pulse drops out; underwater texture; a held note |
| 04 | Warm swell as the mechanism appears |
| 05 | Steady, measured, clearer pitch, almost academic |
| 06 | Resolves to a warm sustained chord on the title; fades under the final line; ends before the brand mark finishes |

## 5. Cue sheet (spotting list)

Times in seconds from the start (150 wpm model); the *Sync* column shows how strictly each cue must hit.

| Time | Frame | Layer | Cue | Level / mix | Sync |
|---|---|---|---|---|---|
| 0.00 | 0 | Ambience | Low room tone / sub bed fades up | −40 dBFS bed | loose |
| 0.00 | 0 | VO | "Two thousand years ago…" | foreground | locked to narration |
| 1.70 | 51 | SFX | First gear engagement (single soft bronze tick) | −24 dBFS peak | **frame-locked** |
| 1.70 | 51 | Music | Single low pulse | −24 LUFS short-term | loose |
| 4.62 | 139 | SFX | Click bed begins as the camera enters the mechanism | −30 dBFS | loose |
| 6.30 | 189 | SFX | Crank turns: ratchet | −26 dBFS | loose |
| 11.30 | 339 | SFX | **Hard cut to underwater:** click bed cuts, underwater ambience in | rapid | **frame-locked** |
| 13.40 | 402 | SFX | Sediment/bubble movement | −32 dBFS | loose |
| 15.00 | 450 | SFX | Dull thud as the lump lifts | −22 dBFS | frame-locked |
| 16.40 | 492 | Music | Warm swell begins | rising | loose |
| 18.40 | 552 | SFX | Metallic slide on the exploded view | −22 dBFS | frame-locked |
| 18.90 | 567 | SFX | Count-up ticks on "82" (about 8 ticks) | −34 dBFS | rhythmic |
| 19.50 | 585 | SFX | Count-up ticks on "30" | −34 dBFS | rhythmic |
| 21.00 | 630 | SFX | Soft settle as the stack closes | −26 dBFS | frame-locked |
| 21.90 | 657 | SFX | Click bed returns, more rhythmic, as the crank turns | −28 dBFS | loose |
| 23.80 | 714 | SFX | Soft tick on D1 diagram reveal | −34 dBFS | frame-locked |
| 26.00 | 780 | SFX | Soft tick on D2 reveal | −34 dBFS | frame-locked |
| 27.90 | 837 | SFX | Gentle chime on the eclipse glyph | −30 dBFS | frame-locked |
| 29.85 | 896 | SFX | **Restrained cinematic impact** at the title | −18 dBFS | frame-locked |
| 29.85 | 896 | Music | Resolve to warm sustained chord | −22 LUFS | loose |
| 36.40 | 1092 | Music | Tension thins as gears ghost out | falling | loose |
| 42.00 | 1260 | SFX | Click bed fades to near-silence | falling | loose |
| 42.50 | 1275 | SFX | Brand mark: one soft tick | −30 dBFS | frame-locked |
| 44.00 | 1320 | Music | Held tone decays by 45.0 s | out | loose |

## 6. Mix and delivery

- **Working target (not a platform specification):** about −14 LUFS integrated for YouTube playback, **true peak ≤ −1 dBTP**. The skill advises against inventing one universal target, so confirm against YouTube's current guidance before mastering.
- **VO** peaks around −6 dBFS before mastering; **music** well beneath; **SFX** below the voice except the reveals.
- Check on phone speakers and headphones. Keep sub-bass modest (phone speakers distort it) and avoid sudden high-frequency spikes.
- **Stems to deliver:** `VO`, `MUSIC`, `SFX`, `AMB`, and the master.
- **Tools (Bible §15):** Audacity for checking and clean-up; FFmpeg for loudness measurement (the `ebur128` filter) and encoding. FFmpeg 6.1.1 is available in this environment; Audacity is not.
- **Re-timing workflow:** after the real VO exists, transcribe it with the installed `remotion-captions` workflow (`transcribe-captions.md`), regenerate `captions/subtitles.srt` and the scene frames, then adjust SFX markers. Never hand-edit just one of them.

## 7. Accessibility

- Burned-in captions carry the speech (sound-off viewing is the default on Shorts).
- Per the installed skill and WCAG guidance, meaningful non-speech sound can also be captioned (e.g. "[gears clicking]"). For this short the sounds add atmosphere rather than information, so they are **not** in the burned-in captions. If a non-speech SDH track is wanted later, add it as a separate `.srt`.
