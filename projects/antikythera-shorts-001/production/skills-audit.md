# Skills Audit — EPOCH & ELEMENT, Shorts 001 pre-production

Date: 2026-11-25 · Branch at audit start: `setup/blender-agent-skills` @ `7ff467e`, clean working tree.

## 1. Repository findings

| Item | Finding |
|---|---|
| Contents before this task | Only `.claude/skills/` (43 skills). No source code, no `package.json`, no Remotion project, no `projects/` folder |
| **Production Bible** | **Not in the repository at audit time.** The studio supplied it afterwards as an upload; it is now stored unchanged at `00_STUDIO/Production_Bible.md` (v0.1) and applied: palette, typefaces, manifest fields and naming, research-brief format, QC checklists |
| Existing project structure | None, so `projects/antikythera-shorts-001/` was created as the brief instructs. The Bible suggests a different working layout (§10.1); see the README |
| `.claude/settings` | None |

## 2. Skills already installed (verified by file check, not by assumption)

All 43 folders have a valid `SKILL.md` with a matching `name:`, and there are no duplicate names. They were installed in earlier commits (`de56c54`, `fa681c9`, `7ff467e`).

| Group | Count | Skills |
|---|---|---|
| **Blender (EL4CTEO)** | 28 | blender-addon-development, blender-animation, blender-asset-qa, blender-character-rigging, blender-clothing, blender-core, blender-environment-kits, blender-export-pipelines, blender-facial-shapekeys, blender-game-optimization, blender-geometry-nodes, blender-hair-grooming, blender-hardsurface-modeling, blender-lighting-lookdev, blender-pbr-materials, blender-pipeline-automation, blender-rendering, blender-retopology-uv, blender-scene-setup, blender-sculpting, blender-simulation, blender-stylized-npr, blender-texture-baking, blender-texturing, blender-time-of-day, blender-video-editing, blender-weather-fx, blender-workflow-recipes |
| **find-skills** (vercel-labs) | 1 | `find-skills` (read in full; it installs nothing itself) |
| **Remotion (official, remotion-dev/skills @ a3f4098)** | 14 | remotion-best-practices (router), remotion-captions, remotion-create, remotion-docs, remotion-elements, remotion-interactivity, remotion-license, remotion-maps, remotion-markup, remotion-multimedia, remotion-render, remotion-saas, remotion-studio, remotion-upgrade |

The Remotion collection **is already complete**: all 14 official skills are present, so nothing from that repository needed adding. Coverage of this project's needs: titles and kinetic text (`remotion-markup`: text-highlights, measuring-text, sequencing, timing, transitions), captions (`remotion-captions`: SRT import, display, transcribe), editable markup (`remotion-interactivity`), audio and SFX (`remotion-markup`: audio, sfx), render (`remotion-render`).

## 3. How find-skills was used

I read `find-skills/SKILL.md` and followed its steps. It was **actually run**: `npx skills find <query>` for 15 queries, with telemetry disabled (`DISABLE_TELEMETRY=1`, `DO_NOT_TRACK=1`). Nothing was installed by the CLI.

| Area | Queries run | Results returned |
|---|---|---|
| Academic / historical research, fact-checking | fact checking · historical research · academic research | 93 · 94 · 98 |
| Documentary writing and storyboarding | documentary script · storyboard | 45 · 96 |
| Blender gears, camera | blender gears · blender camera | 25 · 100 |
| Remotion, kinetic typography | remotion · kinetic typography | 100 · 96 |
| Sound design, voice-over, subtitles | sound design · voice over · subtitles captions | 99 · 57 · 98 |
| Video QC, short-form | video quality · youtube shorts · short form video | 99 · 100 · 97 |

**Limits of the vetting.** The skill's Step 4 asks for install counts, source reputation and GitHub stars. Install counts and licences were checked, and source repositories were cloned and read. **Star counts could not be retrieved**: the GitHub API refused access for repositories not attached to this session. The decisions below therefore rest on content inspection, licence, install counts and fit, not on star counts. Install counts come from the search output and were not independently verified.

## 4. Candidates investigated

| Candidate | Area | Installs (search) | Licence | Decision | Reason |
|---|---|---|---|---|---|
| `calesthio/generative-media-skills@sound-design-foley` | Sound design | 501 | MIT | **INSTALLED** | Fills a real gap (no audio skill existed). Instructions only: no scripts, no commands, no keys. Spotting method, layering, loudness and safety, rights-safe sourcing, captions for non-speech sound; cites standards (ITU-R BS.1770, EBU R 128, W3C WCAG). Used to build `audio/audio-direction.md` |
| `iart-ai/kinetic-typography-skills@kinetic-typography` | Kinetic typography | 5.5K | MIT | Skipped | Near-duplicate of `remotion-markup`'s text and timing guidance; web/CSS/GSAP-first with one Remotion recipe. Adds no capability the installed Remotion skills lack |
| `social-media-skills/skills@short-form-video-script` · `@youtube-shorts` · `@scripting-and-storyboarding` | Short-form scripting, Shorts, storyboards | 3K · 2K · 1.8K | MIT | Skipped | Built for a growth/commercial workflow: depends on sibling skills (`brand-profile`, `voice-builder`) and routes publishing through the **WoopSocial** product. Wrong fit for an educational documentary and would pull in unrelated tooling |
| `guia-matthieu/clawfu-skills@sound-design-film` | Sound design | 966 | MIT | Skipped | Marketing-video oriented (a Walter Murch method applied to marketing video), names an external MCP server (`@clawfu/mcp-skills`) in its metadata, and overlaps with the skill installed |
| `seb1n/awesome-ai-agent-skills@fact-checking` | Fact-checking | 200 | MIT | Skipped | Low adoption; generic True/False verdict scale that conflicts with this project's required four-class confidence scale. The protocol lives in `research/fact-check.md` instead |
| `synthesisengineering/synthesis-skills@synthesis-fact-checking` | Fact-checking | 63 | CC0-1.0 | Skipped | `depends_on` another skill; very low adoption; targets claims in articles, not source-by-source documentary research |
| `moh4696/cinematic-skill@cinematic-film` | Documentary video | 1.8K | MIT | Skipped | Builds narrated films from code as one camera move over a board of documents; a different pipeline from Blender + Remotion |
| `roble3/cc-blender-skill@blender-cameras` (+ the rest of that suite) | Blender camera | 2.3K | MIT | Skipped | Duplicates `blender-lighting-lookdev` / `blender-animation`; its `allowed-tools` are tied to a specific Blender MCP server |
| `elevenlabs/skills@text-to-speech` | Voice-over | 24K | MIT | **Not installed (decision needed)** | Official vendor skill, but it requires a paid ElevenLabs account and `ELEVENLABS_API_KEY`, would send the script to a third party, and the narrator choice (human or synthetic) has not been made. Revisit when that decision is taken |

**Seen in the search listings but not investigated** (only the top results per query were reviewed; these were not opened, so no verdict is claimed): `shubhamsaboo/awesome-llm-apps@academic-researcher`, `heygen-com/hyperframes@*`, `josiahsiegel/claude-plugin-marketplace@ffmpeg-captions-subtitles`, `mattpocock/skills@research`, `scenario-labs/skills@scenario-blender-previs-storyboard`, `bitwize-music-studio/claude-ai-music-skills@researchers-historical`. A follow-up pass could open these.

## 5. Installed in this task

| Skill | Path | Files | Source | Licence | Dependencies |
|---|---|---|---|---|---|
| `sound-design-foley` | `.claude/skills/sound-design-foley/` | `SKILL.md`, `EVAL.md` (unmodified; byte-identical to upstream, checked with `diff -r`) | https://github.com/calesthio/generative-media-skills, path `skills/production/audio-craft/sound-design-foley`, commit `8c85352` | MIT | **None.** It is guidance only: no scripts, no packages, no API keys. `EVAL.md` is a scoring guide, not executable |

Installed at **project level** only. Nothing global. No existing skill, file or branch was changed. After installation: 44 skills, no duplicate names.

## 6. Capability map for this project

| Need | Covered by |
|---|---|
| Source-by-source research and fact-checking | **No skill.** Done by explicit protocol in `research/fact-check.md`, `research-brief.md` and `sources.md`; the confidence scale is the project's own and follows Bible §8 |
| Documentary writing and storyboard | **No dedicated skill.** Done by hand against the brief and the Bible; `blender-workflow-recipes` informs the shot logic |
| Blender gears, hero asset, lighting, camera, render | The 28 Blender skills (see `design/blender-art-direction.md` §10) |
| Remotion titles, diagrams, captions | The 14 Remotion skills |
| Sound design and SFX plan | **`sound-design-foley`** (new) |
| Voice-over | Human or licensed TTS; **open decision** (no skill installed on purpose) |
| Subtitles | `remotion-captions` (SRT import, transcribe) + `captions/subtitles.srt` |
| Visual / video QC | `blender-asset-qa` for 3D; manual checklist in `production/quality-control.md` (which crosswalks Bible §12) for the rest |

## 7. Dependencies and requirements

| Requirement | Status in this environment |
|---|---|
| Node.js / npm | Present (Node 22.23.5, npm 10.9.9) |
| ffmpeg / ffprobe | Present (6.1.1) |
| Python 3 | Present (3.13) |
| **Blender 5.2 LTS+** | **Missing.** Not needed for pre-production; install before modelling (see Blender spec §13) |
| Remotion npm packages and headless Chrome | **Not installed.** Installed when the project is scaffolded |
| Audacity (Bible §15) | Not installed |
| GPU for Cycles | **None** here (4 CPU cores, no GPU) |
| GitHub API access to third-party repos | **Refused** (star counts unavailable) |
| UCL 2021 page | **Blocked** (HTTP 403) |

## 8. Exact installation locations

- New: `/home/user/epoch-and-element/.claude/skills/sound-design-foley/` (`SKILL.md`, `EVAL.md`)
- Unchanged: the 43 existing folders under `/home/user/epoch-and-element/.claude/skills/`
- Also new, not a skill: `/home/user/epoch-and-element/00_STUDIO/Production_Bible.md` (an unmodified copy of the studio's upload)
- Git: all changes are **uncommitted** on branch `setup/blender-agent-skills`.
