# vaccine-pv-matrix

A structured reference for vaccine pharmacovigilance. It shows which sections of the WHO–ISoP Pharmacovigilance Curriculum (2026) attach to each function of vaccine pharmacovigilance, and lays a roadmap frame over those functions using the WHO global smart pharmacovigilance strategy (2025).

**Version 0.1 · 20 October 2026 · draft for review by the ISoP Vaccine Special Interest Group**

The one-page function map is `index.html` (published with GitHub Pages at <https://suahcheon.github.io/vaccine-pv-matrix/>).

This is independent work built on WHO and WHO–ISoP documents. It has not been reviewed or endorsed by WHO or ISoP.

## What is here

| Path | What it is | Licence |
| --- | --- | --- |
| `index.html` | One-page function map: functions, attached curriculum sections, GVSB1.0 capacity, reference-board status | CC BY-NC-SA 4.0 |
| `data/function-map/functions.csv` | The function axis: 33 functions in three layers, plus 2 setting tags and 5 non-function values | CC BY-NC-SA 4.0 |
| `data/curriculum/nodes.csv`, `edges.csv` | The 2026 curriculum as a graph: 26 chapters, 3 part headings, 107 sections, 52 subsections; 181 edges declared by the document. Sections and AI subsections carry a function assignment (`my_function`) | CC BY-NC 4.0 |
| `data/roadmap/stages.csv` | Stage axis: Smart PV strategy Figure 4 (maturity × term) and GVSB2.0 Annex 1 (minimal and enhanced capacity) | CC BY-NC-SA 4.0 |
| `data/roadmap/capacity-elements.csv` | The 13 capacity elements of GVSB2.0 Annex 1, linked to functions | CC BY-NC-SA 4.0 |
| `data/roadmap/actions.csv` | The 61 actions of Smart PV strategy Tables 2–5 (pp. 22–27), verbatim, with table, column and item location, the GBT sub-indicators the document cites, and the author's function links | CC BY-NC-SA 4.0 |
| `data/roadmap/frame.csv` | Function × stage frame: for each function, its curriculum sections, GVSB1.0 capacity, reference-board status, and the Table 2–3 vaccine actions placed by stage. Country cells are left empty | CC BY-NC-SA 4.0 |

All files are UTF-8 CSV and open without a graph database.

## What the map shows

- Six of the twelve functions that GVSB1.0 lists as minimal capacity have one curriculum section or none. Build-up systems need these first.
- Reporting (IV.1A), investigation (IV.2A) and causality assessment (IV.3A) are all minimal-capacity functions, and the Smart PV strategy places all three in the short term for systems below maturity level 3 (Table 2, p. 22). Passive surveillance standardization is proposed as the first roadmap task.
- AI applications in curriculum section 18.3 attach only to the front of the data flow (intake, coding, data quality, causality, signals). None attach to decisions or communication.
- In the WHO example plans for a new vaccine (Tables 2 and 3), no action reaches immunization policy, and only one reaches regulatory decisions based on vigilance information (GBT VL05.01), as a secondary link.

## Why a structured, machine-readable reference?

Most readers will use the one-page map, not the graph files behind it. The structure is there for a different reader: AI assistants. Many countries building up vaccine pharmacovigilance have very few trained staff, and AI tools are already being used to fill that gap, often without a reliable anchor in international standards. By mapping the WHO–ISoP curriculum, the Global Vaccine Safety Blueprint and the GBT into one open, versioned structure, the reference can later be exposed through the Model Context Protocol, so that an assistant answers questions such as "which curriculum sections and WHO manuals support AEFI investigation?" by following the map and citing the version and source it relied on. Each country still decides how and when to publish its own assessment.

## How it was built

**Function axis.** The Smart PV strategy has no function classification of its own and states in four places that it builds on the Global Vaccine Safety Blueprint. The axis therefore uses the strategic areas, objectives and strategies of GVSB2.0 Annex 3 (pp. 37–42). Objectives 1–3 of strategic area IV are split to strategy level (IV.1A, IV.1B, …) because they group steps of the data flow together. Two regulatory decisions that GVSB2.0 does not list as objectives come from GBT sub-indicators VL04.07 and VL05.01. The pre-authorisation layer refers to the GBT functions for clinical trial oversight and marketing authorization. Immunization policy (`MY-IP`) is the only function without a source ID; it is grounded in GVSB2.0 p. 1, II.3 (p. 13) and V.3 (p. 27). Strategic area VI is kept as a setting tag, not a function.

**Curriculum sections.** Each of the 107 sections was assigned by five ordered questions: is it an activity of the system; knowledge needed for a function; adjacent to pharmacovigilance at a defined interface; an AI method; or none of these. Notation in `my_function`: `A | B` main and secondary function; `A & B` parallel (only where the source places two decision-makers side by side); `ai_application > X` an AI application that sits on function X.

**Reference board.** "Thin (candidate)" means exactly one curriculum section. Section count is a screening rule only. Whether that one section covers what the function requires is checked against the source documents and in review.

**Roadmap frame.** Stages come from Smart PV strategy Figure 4 (p. 16) and GVSB2.0 Annex 1, "GVSB1.0: minimal and enhanced capacity" (p. 33). The action rows are the example institutional development plans in Tables 2–5.

**Two kinds of values.** Columns named `src_*` or `source_*`, and edges with `origin = declared`, hold what the source document gives. Columns named `my_*`, and links with `origin = interpreted`, hold the author's interpretation and are open to review. The curriculum edges are all declared by the document.

## Notes on the sources

Printing issues are kept as printed and noted in `my_note`:

- Smart PV strategy Table 3: the long-term column header is printed "(<5 years)"; the other tables print ">5 years".
- Table 2: "Vl04.04". Table 4: "EUM4all" (the EMA procedure is EU-M4all). Table 5: "Survey to understanding".
- Table 5 cites VL04.05 (staff access to information resources) for "Monitor the usage of product Z"; the text on p. 26 describes drug utilization studies, so the citation looks mismatched.
- Curriculum Table 1: subsection 16.3.2 is printed "13.3.2"; 9.3.2 and 14.2.4 carry stray characters; 7.2 and 7.4 carry a colon. IDs are corrected and the printed form is kept.

## Questions for reviewers

1. Does the function list cover vaccine pharmacovigilance completely? What is missing?
2. Is the way functions are attached to curriculum sections right?
3. Does placing passive surveillance standardization first for build-up countries match your experience?

Functions with no curriculum section, or only one, are listed on the map as places where vaccine-specific material could attach.

## Licences and attribution

This repository contains material from three licensed sources, used under their terms:

- **WHO–ISoP Pharmacovigilance Curriculum.** Beckmann J, Tuccori M, Bahri P, et al. *The WHO-ISoP Pharmacovigilance Curriculum: 2026 Update.* Drug Safety. 2026. doi:10.1007/s40264-026-01717-y. © The Author(s) 2026, CC BY-NC 4.0. `data/curriculum/` contains the section headings verbatim and adds structure and columns named `my_*`. It is shared under CC BY-NC 4.0 (<https://creativecommons.org/licenses/by-nc/4.0/>).
- **Global vaccine safety blueprint 2.0 (GVSB2.0) 2021–2023.** Geneva: World Health Organization; 2021. Licence: CC BY-NC-SA 3.0 IGO.
- **The global smart pharmacovigilance strategy.** Geneva: World Health Organization; 2025. Licence: CC BY-NC-SA 3.0 IGO.

The function axis, the map and the roadmap frame adapt the two WHO documents. CC BY-NC-SA 3.0 IGO, section 4(b), allows an adaptation to be shared under a later version with the same licence elements, so these files are shared under CC BY-NC-SA 4.0 (<https://creativecommons.org/licenses/by-nc-sa/4.0/>). `data/roadmap/actions.csv` reproduces the text of Smart PV strategy Tables 2–5 with its location; other GVSB2.0 and strategy content is shortened or paraphrased. Changes made: functions split and shortened, function links and curriculum links added by the author.

This is an adaptation of original works by WHO. Views and opinions expressed in this adaptation are the sole responsibility of the author and are not endorsed by WHO. No WHO or ISoP logo is used.

The WHO Global Benchmarking Tool (Revision VI, 2021) is referenced by sub-indicator number, title and page only. No other text from it is reproduced.

See `LICENSE.md` for the file-by-file licence.

## How to cite

See `CITATION.cff`. A DOI will be added when the first release is archived.

## Next

- Revise the map and frame with review comments (v0.2).
- Passive surveillance column: for each standard (WHO AEFI surveillance procedures, ICH E2B(R3), MedDRA, Brighton Collaboration case definitions, WHO AEFI causality assessment, observed-to-expected analysis), what has to apply, linked to curriculum sections and source documents.
- A read-only Model Context Protocol server over released versions, once the map is stable.

## Author

Myeong-eun (Suah) Cheon, MD. Korea Disease Control and Prevention Agency (KDCA). Member, ISoP Vaccine SIG. This repository is the author's own work and does not represent an official position of KDCA.

Comments and corrections are welcome as GitHub issues.
