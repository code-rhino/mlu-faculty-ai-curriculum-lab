# Lab 2 Sample PDFs

This folder holds the six discipline-specific sample documents used in **Lab 2: Build a Discipline-Specific AI Teaching Assistant** (`../seminar-lab2-discipline-assistant.ipynb`).

## Why these exist

Per the locked Lab 2 design decisions (see `../SEMINAR_PLAN.md`), we do **not** rely on attendees bringing their own PDFs. Every participant gets a pre-staged, license-clean sample matched to their persona.

## The six samples

| Persona | Filename | Status | Owner | Source |
|---|---|---|---|---|
| 1. Dentistry | `persona1_dentistry_perio_case.pdf` | ✅ Staged | — | Cureus 2026 case report (CC-BY 4.0): "Clinical Management of Localized Aggressive Periodontitis with Esthetic Replacement of Tooth 11 Using a Resin-Bonded Bridge" — Abulfateh et al. |
| 2. Computer Science | `persona2_cs_data_structures.pdf` | ✅ Staged & tested | — | Open Data Structures by Pat Morin (CC-BY), Ch. 1 extract |
| 3. English Literature | `persona3_english_victorian_essay.pdf` | ⬜ Not staged | — | — |
| 4. Nursing | `persona4_nursing_pharmacology.pdf` | ⬜ Not staged | — | — |
| 5. Business | `persona5_business_leadership_case.pdf` | ⬜ Not staged | — | — |
| 6. Biology | `persona6_biology_lab_protocol.pdf` | ⬜ Not staged | — | — |

Each sample has its own `.md` placeholder in this folder with sourcing requirements. Replace the `.md` placeholder with the actual `.pdf` when sourced. Update the table above with status + owner + source.

## Universal requirements (apply to all six)

- **License:** Public domain, CC-BY, CC-BY-SA, or explicit open-access. **No** copyrighted textbooks, Harvard Business cases, paywalled journal articles, etc.
- **Length:** 8–30 pages. Hard cap **50 pages** — enforced by embedding-time budget in the notebook.
- **Format:** Text-based PDF (not scanned image-only). The `PyPDFLoader` won't read scanned PDFs reliably. If you find scanned material, OCR it first.
- **Content quality:** Realistic to actual teaching workflow. Should be the kind of document a real faculty member in that discipline would hand to a student or TA.
- **Demo readiness:** When you ask "what are the key concepts here?" the AI should produce a non-trivial, impressive answer. Test before staging.

## Test each PDF before the seminar

For each sample:
1. Drop the file into this folder.
2. Open `../seminar-lab2-discipline-assistant.ipynb`.
3. Set `pdf_path = "data/personaX_..."`.
4. Run through Parts 3 and 4 end-to-end.
5. Confirm:
   - [ ] Loads without errors
   - [ ] Chunks to 15–60 chunks (rough sanity range)
   - [ ] Embedding completes in < 90 seconds
   - [ ] Quiz/study guide/rubric outputs are substantive
   - [ ] Grounded vs. vanilla comparison shows a meaningful difference
