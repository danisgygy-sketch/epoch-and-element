# Blender Art Direction — Antikythera Mechanism (Hero Asset)

Status: **specification only. Nothing has been modelled or rendered.** Blender is **not installed** in this environment (checked: `blender` not on PATH). It was not needed for pre-production; see §11 for the install and smoke-test plan.

**Brand source.** The look follows the Production Bible (`00_STUDIO/Production_Bible.md`, §4.1–4.3 and §5): cinematic stylised realism, readable first, controlled detail, restrained material and lighting effects, and the Midnight Navy / Deep Blue / Antique Gold / Scientific Cyan palette for the world and overlays. Bronze is a *material*, not a brand colour. Lens, light and material values are this project's proposals.

---

## 1. Visual thesis

A serious, quiet, museum-grade look: dark navy space, a single warm key, bronze that reads as *metal that is 2,000 years old*, never as gold or plastic. The camera behaves like a macro cinematographer: slow, deliberate, always showing how two parts relate. Every shot must teach something about the mechanism or about how we know.

**Avoid:** low-poly appearance · plastic or chrome-looking bronze · excessive bloom · over-saturated yellow-gold · random decorative gears with no mechanical or educational purpose · invented inscriptions or details presented as fact.

## 2. Evidence-based reconstruction vs artistic visualisation

This is the project's central design rule. Every object is assigned a tier (see `research/fact-check.md`) and the tier controls its **material, damage, and labelling**.

| Tier | Meaning | Objects | Material treatment | Labelling |
|---|---|---|---|---|
| **A** | Surviving evidence | Corroded fragments in scene 04; the surviving gear trains shown in the layered exploded view | Aged bronze with real damage, crust and patina; visible loss | none needed |
| **B** | Inferred from evidence | Hand crank, case, completing gear planes needed to close the train, back-dial plate surfaces | Clean matte bronze, light tarnish only, no corrosion | "artist's reconstruction" in the description |
| **C** | Published hypothesis | The 2021 front planetary layers, the Dragon Hand for the Moon's nodes | **Ghosted**: translucent Scientific Cyan (`#56C6DF`) emissive wireframe, never solid | on-screen **RECONSTRUCTION** chip in scene 06 |
| **D** | Dramatisation | Seabed, wreck, timbers, amphorae, the corroded lump in scene 03 | Stylised realism, desaturated teal | **DRAMATIZED RECONSTRUCTION** label |

**Rules.** (1) Never place Tier C geometry in solid bronze. (2) Never invent Greek text: use abstract tick-mark engraving, or a transcription verified against the Antikythera Mechanism Research Project data. (3) Do not use scans or photographs of the real fragments; the fragments are original sculpts "inspired by" the published imagery. (4) No gear count on screen other than 82 fragments and 30 surviving gears (the model itself will contain more gears, because it must be mechanically complete; none are labelled as historical fact).

## 3. Hero asset specification

**Asset ID:** `EE_S001_MODEL_Antikythera_Main_v01` (Bible §10.2 naming) · **Units:** metric, 1 Blender unit = 1 m (`blender-scene-setup`) · **Scale:** real-world; case envelope 0.33 × 0.18 × 0.10 m (the Ministry's "possible dimensions", Tier B).

Two states of the same asset, driven by a custom property `state` (0 = fragment, 1 = reconstruction):

| State | Used in | Geometry | Notes |
|---|---|---|---|
| **F — Fragmented** | Scene 03–04 | Three main fragment groups (A, B, C) + scattered minors, built as sculpts with displacement | Proportions follow published fragment sizes: A 0.177 m, B 0.118 m, C 0.105 m (maximum dimensions, Ministry) |
| **R — Reconstructed** | Scenes 01, 02, 04–06 | Complete gear train, dials, pointers, crank, plates, case | Parametric: every gear is generated, not hand-sculpted |

**Level of detail:** hero close-ups hold 0.05 mm tooth detail; wide shots use a lighter LOD swapped by distance. Target budget: under 6 M triangles visible per hero frame.

## 4. Modelling breakdown

All gears come from **one parametric generator** so teeth, spokes and meshing stay consistent.

| Module | Build method | Skills | Tier | Notes |
|---|---|---|---|---|
| **M1 Gear generator** | Geometry Nodes tree with inputs: tooth count, outer radius, root radius, thickness, hub radius, spoke count, tooth phase | `blender-geometry-nodes` (JSON builder), `blender-hardsurface-modeling` | A/B | Teeth are **triangular** (as published); the numbers come from the publications, never guessed (see open item 1) |
| **M2 Gear trains** | A table (CSV/JSON) of (gear, teeth, axis, layer, meshes-with); script places every gear and sets its tooth phase so neighbours mesh | `blender-geometry-nodes`, `blender-pipeline-automation` | A/B | Only trains needed on screen are fully detailed; the remainder is a lower LOD |
| **M3 Dials and plates** | Flat bronze plates with engraved scales; text as tick-mark geometry only | `blender-hardsurface-modeling`, `blender-texturing` (decals) | B | Zodiac and calendar rings use tick marks and verified words only |
| **M4 Pointers and the lunar pin-and-slot** | Hand-modelled hero mechanism for the Moon's variable speed | `blender-hardsurface-modeling` | A (evidence: Nature 2006) | The macro hero of scene 05: pin on an epicyclic gear sliding in a slotted lever |
| **M5 Crank** | Simple handle and shaft | `blender-hardsurface-modeling` | B | Visibly a reconstruction (cleaner than the rest). Optional: script v2 no longer mentions the crank |
| **M6 Case** | Wooden frame with bronze plates | `blender-hardsurface-modeling`, `blender-pbr-materials` | B | Possible dimensions only |
| **M7 Fragments** | Sculpt + displacement + crust | `blender-sculpting`, `blender-texturing` | A | Original sculpt; no scans |
| **M8 Ghost layer** | Duplicate of the Tier C gears with a wireframe + emission shader | `blender-pbr-materials`, `blender-stylized-npr` | C | Toggle by collection; in scene 06 the transition `solid → ghost` animates the shader mix |
| **M9 Environment** | Seabed, a few amphora shards, timber ribs, rock | `blender-environment-kits`, `blender-sculpting` | D | Minimal, readable, vertical-first |

## 5. Materials

Use `blender-pbr-materials` and its `pbr-values.md`. The reference table lists copper as base colour (0.955, 0.638, 0.538) with roughness 0.2–0.45; bronze is not listed, so these are **proposed** values:

| Material | Metallic | Base colour direction | Roughness | Extras |
|---|---|---|---|---|
| Clean aged bronze (Tier B) | 1.0 | warm, slightly desaturated copper-brown (reference copper ×0.85) | 0.35–0.50 | micro-scratch normal, subtle edge wear |
| Corroded bronze (Tier A) | 0.0 for crust, 1.0 for exposed metal (mask-blended) | green-teal crust over brown metal | 0.55–0.85 | cavity-driven crust, bump + displacement |
| Wood (case) | 0.0 | dark aged oak | 0.6–0.75 | restrained |
| Ghost (Tier C) | 0.0 | Scientific Cyan `#56C6DF` emissive, alpha 0.25–0.4 | n/a | wireframe + fresnel rim |
| Seabed / rock | 0.0 | desaturated sand-teal | 0.7–0.9 | stylised, low saturation |

**Hard limits:** no over-saturated yellow; bronze highlights stay below clip; patina is restrained and occupies recesses first. Judge materials only under a neutral HDRI (`blender-lighting-lookdev` turntable) before lighting for effect.

## 6. Animation plan

**Single-driver principle.** The crank angle is the only keyframed value. Every gear's rotation is a **driver** derived from it, `θ_j = -θ_i × (N_i / N_j)` for meshing pairs and equal rotation for gears fixed to the same arbor. This guarantees physically believable engagement and makes retiming trivial (`blender-animation`).

| Item | Method |
|---|---|
| Gear meshing | Tooth-phase offset set per pair so teeth interlock; verify with a contact check at 12 sampled angles |
| Interpenetration QA | `blender-asset-qa` collision/overlap pass at those 12 angles; fail if any tooth overlaps by more than a set tolerance |
| Pointer motion | Derived from dedicated gears via drivers (Sun pointer slow, Moon pointer faster) |
| Lunar variable speed | The pin-and-slot linkage animated from the epicyclic gear's rotation, not keyed |
| Exploded view | Collection-level offsets keyed along the gear axis in scene 04 |
| Loops | `loop_check.py` (from `blender-animation`) on any looping gear background |
| Speeds | One nominal crank speed (about one turn per 3 s), eased in and out only at scene boundaries |

**Evidence note.** The animated speeds are illustrative; they show *how* gears turn, not the historical rate of use.

## 7. Lighting

Use `blender-lighting-lookdev` and `blender-time-of-day` (its underwater mood).

| Scene | Setup |
|---|---|
| 01–02 (macro) | One warm key (≈3,200 K) at a raking angle to bring out teeth; a cool navy fill at low intensity; a narrow rim for separation; volumetric beam kept thin (density low) |
| 03 (underwater) | A teal-blue sun shaft from above (a god-ray volume), particulate "marine snow" (reuse the dust technique in `blender-weather-fx`), blue-green attenuation with distance |
| 04 (reveal) | The beam warms as the fragments separate; clean three-point logic on the exploded mechanism |
| 02 (diagram plate) and 05 | Even, shallow-contrast lighting so the 2D overlays read; scene 05 is the same set-up with the ghost layer toggled on |
| 06 | Museum lighting: a soft warm key, a narrow rim, dark navy world; subtle reflections on bronze (HDRI of a dim studio) |

**World colour (Bible §4.3):** Midnight Navy `#101A2A` world, Deep Blue `#172D46` for the underwater and secondary layers, Scientific Cyan `#56C6DF` for the hypothesis ghost. Bronze highlights come from the material under the key light: keep them below clipping and well short of Antique Gold's saturation. AgX view transform; judge saturation on a phone-sized preview.

## 8. Cameras

Vertical frame, 1080 × 1920, sensor fit set so the **height** drives field of view.

| Use | Lens | Aperture | Move | Notes |
|---|---|---|---|---|
| Macro | 85–100 mm | f/2.8–4 | Slow push (≤ 4% scale) | Keep at least one full tooth sharp; never a total blur |
| Mechanism travel | 35–50 mm | f/4–5.6 | Track + slight roll (< 2°) | Parallax between layers does the 3D work |
| Reveal / orbit | 50 mm | f/5.6 | 20–30° low orbit | Slow; ease only at ends |
| Underwater | 35 mm | f/5.6 | Lateral dolly | Slight vignette; haze with depth |

**Depth of field:** focus on the *teaching element* (the meshing teeth, the pointer). Important text is never placed over blurred regions. For 2D leader lines, export per-frame screen positions of anchor empties (see `remotion-art-direction.md` §6).

## 9. Render settings (proposed)

| Item | Value |
|---|---|
| Resolution / fps | 1080 × 1920, 30 fps (nominal 1,440 frames; cap 1,650) |
| Engine | **Cycles** for hero macro and reveal; **EEVEE** for the underwater scene and all non-hero plates |
| Samples | 128–256 with denoising; adaptive sampling on |
| Colour | AgX, 16-bit PNG sequences (or high-bitrate intermediate) per shot |
| Passes | Beauty, plus Z (depth) and one anchor/mask pass for pointer highlights |
| Deliver to Remotion | Per-shot image sequence or intermediate video, with a JSON of projected anchor positions |

**Render budget (estimates, not measurements).** This container has 4 CPU cores and no GPU, so final Cycles rendering here is not practical. Plan a GPU machine or a cloud farm. Cycles hero frames at this complexity are commonly in the tens of seconds to a few minutes per frame on a modern GPU, which for roughly 600–700 hero frames is an hours-scale job, not days. Verify with a test frame before committing to a number.

## 10. Required Blender skills

Installed and mapped to work packages:

| Package | Skills |
|---|---|
| Setup | `blender-core`, `blender-scene-setup` |
| Gear generator, hero modelling | `blender-geometry-nodes`, `blender-hardsurface-modeling`, `blender-sculpting` (fragments) |
| Materials and wear | `blender-pbr-materials`, `blender-texturing`, `blender-texture-baking` |
| Underwater / marine snow | `blender-time-of-day`, `blender-weather-fx`, `blender-environment-kits` |
| Lighting and cameras | `blender-lighting-lookdev`, `blender-rendering` |
| Animation | `blender-animation` |
| Ghost / stylised layer | `blender-stylized-npr` |
| QA and delivery | `blender-asset-qa` (mandatory gate), `blender-pipeline-automation`, `blender-export-pipelines`, `blender-workflow-recipes` (product turntable, mood shots) |

No additional Blender skills are needed.

## 11. Asset list

Authoritative list: `production/asset-manifest.csv` (Bible §10.3 fields, §10.2 naming). The Blender-side assets are the hero asset (states F/R), the gear generator and gear table, crank, case, fragments A/B/C plus minors, the seabed set, the four materials (clean bronze, corroded bronze, wood, ghost) and the camera rig.

## 12. Complexity estimate (relative)

| Work package | Complexity | Main risk |
|---|---|---|
| Gear generator + meshing validation | **High** | Tooth-phase alignment for every pair |
| Hero mechanism + dials | **High** | Showing real detail without inventing history |
| Corroded fragments | Medium | Convincing crust without scan data |
| Underwater scene | Medium | Readability in a vertical frame |
| Ghost / evidence legend | Low–Medium | Keeping it clear at phone size |
| Camera and lighting | Medium | Consistency across shots |
| Render and delivery | Medium | GPU access and iteration time |

## 13. Environment and next steps for Blender

1. **Install headless Blender** (5.2 LTS or newer; 5.3 preferred) in a GPU-capable environment. Not done here because pre-production did not need it.
2. Set `BLENDER_EXE`, then run `blender-core/scripts/run_in_blender.py --which` and `env_report.py` to confirm.
3. **Smoke test the generator** in headless mode: two meshing gears, 12-angle collision check, one 960 × 1704 draft frame.
4. Only after step 3 passes, start the hero asset.

## 14. Open items

1. **Gear data.** Tooth counts, radii and arbors must be transcribed from a published source (Freeth 2006 full text, SR21 Supplementary Table S8, or AMRP data). **Nothing in this document is a tooth count.**
2. **Case and crank design** are inferred; get a second source before finalising.
3. **Inscriptions.** Decide tick marks vs verified transcription.
4. **Brand mark.** None exists yet (the Bible's `Brand_Assets/` is empty); the end card uses a wordmark.
