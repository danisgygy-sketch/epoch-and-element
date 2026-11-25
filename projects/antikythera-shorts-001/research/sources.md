# Source Register — Shorts 001

Last checked: 2026-11-25. "Access" records what we **actually retrieved**, not what we intended to read.

## A. Required sources

| ID | Source | URL | Type | Access | Used for |
|---|---|---|---|---|---|
| S1 | Greek Ministry of Culture — *The Antikythera Mechanism* (catalogue entry, NAM Athens inv. Χ 15087) | https://olympicgames.culture.gov.gr/en/texnologia/1_Mixanismos-Antikithirwn.html | Official museum/ministry catalogue | **Full page read** (about 320 words) | 82 fragments, 30 gears, "probably 150–100 BC", bronze, case dimensions, provenance "January 1901", instructions on plates, "earliest preserved portable astronomical calculator" |
| S2 | Freeth et al., *Decoding the ancient Greek astronomical calculator known as the Antikythera Mechanism*, Nature (2006) | https://www.nature.com/articles/nature05357 | Peer-reviewed | **Abstract, figure captions and references only** (paywall) | Eclipse prediction (Babylonian cycles), planetary display "now lost", Hipparchos lunar theory in the gearing, "more complex than any known device for at least a millennium", discovery 1901 |
| S3 | Seiradakis & Edmunds, *Our current knowledge of the Antikythera Mechanism*, Nature Astronomy (2018) | https://www.nature.com/articles/s41550-017-0347-2 | Peer-reviewed review | **Abstract, figure captions and references only** (paywall) | Wreck 1900, recognised 1902, "oldest known mechanical calculator", agreement on solar/lunar functions, planets intended, "major uncertainties" |
| S4 | UCL News (2021) — *Experts recreate a mechanical Cosmos for the world's first computer* | https://www.ucl.ac.uk/news/2021/mar/experts-recreate-mechanical-cosmos-worlds-first-computer | University press release | **NOT READ.** HTTP 403 on direct requests (two attempts with different client headers) and via a separate fetch agent | Nothing. **Do not cite in the description until it has been read.** |
| S5 | Freeth et al., *A Model of the Cosmos in the ancient Greek Antikythera Mechanism*, Scientific Reports (2021) | https://www.nature.com/articles/s41598-021-84310-w | Peer-reviewed, open access | **Full text read** (about 12,000 words, supplementary material not read) | 82 fragments / 30 gears / one third survives, Fragment A has 27 gears, the 34 + 35 = 69-gear model, nine outputs, the evidence-vs-hypothesis wording, Saros/Metonic dials, "User Manual" on the back cover |

## B. Additional sources

| ID | Source | Access | Status |
|---|---|---|---|
| S6 | Wikipedia, *Antikythera mechanism* | Read through a sub-agent, partly as a model summary | **Lead-finder only.** Never evidence. Used to discover the dating debate, discovery timeline and crank question. Every point taken from it is flagged `[2nd]` in `fact-check.md`. |
| S7 | National Archaeological Museum, Athens (namuseum.gr) | Home page only; no mechanism page located | Open: find the museum's own Antikythera page. |
| S8 | University of Cambridge news archive | Index page only; the 2021 item was not found | Open |
| S9 | Jones, A., *The Epoch Dates of the Antikythera Mechanism*, ISAW Papers 17 (2020) | **Not read.** Listed in the Ministry bibliography | To retrieve for the dating debate |
| S10 | de Solla Price, *Gears from the Greeks*, Trans. Am. Phil. Soc. 64.7 (1974/75) | **Not read.** Listed in the Ministry bibliography | Background only |

## C. Retrieval log

| Attempt | Result |
|---|---|
| Ministry page, direct | 200, read |
| Nature 2006, direct | 200, abstract only |
| Nature Astronomy 2018, direct | 200, abstract only |
| Scientific Reports 2021, direct | 200, full text |
| UCL 2021, direct (default headers) | **403** |
| UCL 2021, direct (browser headers) | **403** |
| UCL 2021, fetch agent | **403** |

## D. Description-ready source list

Only sources actually read may be listed. Add UCL only after item S4 is read.

```
Sources
• Greek Ministry of Culture: The Antikythera Mechanism — https://olympicgames.culture.gov.gr/en/texnologia/1_Mixanismos-Antikithirwn.html
• Freeth et al., Nature (2006) — https://www.nature.com/articles/nature05357
• Seiradakis & Edmunds, Nature Astronomy (2018) — https://www.nature.com/articles/s41550-017-0347-2
• Freeth et al., Scientific Reports (2021) — https://www.nature.com/articles/s41598-021-84310-w
```

## E. Rules

1. No quotation appears in the video, description or pinned comment unless it is copied from a source tagged **Full** or **Abstract** here.
2. Secondary sources (S6) can suggest a lead. They cannot support a claim.
3. Numbers on screen must trace to a `fact-check.md` row marked **Established**.
4. Images and 3D scans of the real fragments are **not** used. All visuals are original artwork (see `production/asset-manifest.csv`).
