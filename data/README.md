# Lab 2 Sample PDFs

This folder holds the six discipline-specific sample documents used in **Lab 2: Build a Discipline-Specific AI Teaching Assistant** (`../curriculum-embedding-lab.ipynb`).

## Why these exist

Per the locked Lab 2 design decisions (see `../SEMINAR_PLAN.md`), we do **not** rely on attendees bringing their own PDFs. Every participant gets a pre-staged, license-clean sample matched to their persona.

## The six samples

| Persona | Filename | Status | Owner | Source |
|---|---|---|---|---|
| 1. Dentistry | `persona1_dentistry_perio_case.pdf` | ✅ Staged | — | Cureus 2026 case report (CC-BY 4.0): "Clinical Management of Localized Aggressive Periodontitis with Esthetic Replacement of Tooth 11 Using a Resin-Bonded Bridge" — Abulfateh et al. |
| 2. Computer Science | `persona2_cs_data_structures.pdf` | ✅ Staged & tested | — | Open Data Structures by Pat Morin (CC-BY), Ch. 1 extract |
| 3. English Literature | `persona3_english_victorian_essay.pdf` | ✅ Staged | — | Mary Seacole, *Wonderful Adventures of Mrs. Seacole in Many Lands* (1857), Chs. I–IV. Public domain via Project Gutenberg (eBook #23031). |
| 4. Nursing | `persona4_nursing_pharmacology.pdf` | ✅ Staged | — | Original instructional material authored for this seminar (cardiovascular pharmacology). License-clean; no rights reserved. |
| 5. Business | `persona5_business_leadership_case.pdf` | ✅ Staged | — | Original fictional teaching case authored for this seminar ("Northwind Logistics"). License-clean; all figures/people invented. |
| 6. Biology | `persona6_biology_lab_protocol.pdf` | ✅ Staged | — | Original wet-lab protocol authored for this seminar (agarose gel electrophoresis). License-clean; no rights reserved. |

All six samples are staged as `.pdf`. Personas 1–3 use sourced open/public-domain documents; personas 4–6 use original license-clean material authored for the seminar. (Earlier `.md` placeholders held sourcing specs and have been removed now that the PDFs are in place.)

## Universal requirements (apply to all six)

- **License:** Public domain, CC-BY, CC-BY-SA, or explicit open-access. **No** copyrighted textbooks, Harvard Business cases, paywalled journal articles, etc.
- **Length:** 8–30 pages. Hard cap **50 pages** — enforced by embedding-time budget in the notebook.
- **Format:** Text-based PDF (not scanned image-only). The `PyPDFLoader` won't read scanned PDFs reliably. If you find scanned material, OCR it first.
- **Content quality:** Realistic to actual teaching workflow. Should be the kind of document a real faculty member in that discipline would hand to a student or TA.
- **Demo readiness:** When you ask "what are the key concepts here?" the AI should produce a non-trivial, impressive answer. Test before staging.

## Test each PDF before the seminar

For each sample:
1. Drop the file into this folder.
2. Open `../curriculum-embedding-lab.ipynb`.
3. Set `persona = "X"` in the "Set your persona number" cell.
4. Run through Parts 1 and 2 end-to-end.
5. Confirm:
   - [ ] Loads without errors
   - [ ] Chunks to 15–60 chunks (rough sanity range)
   - [ ] Embedding completes in < 90 seconds
   - [ ] Quiz/study guide/rubric outputs are substantive
   - [ ] Grounded vs. vanilla comparison shows a meaningful difference
