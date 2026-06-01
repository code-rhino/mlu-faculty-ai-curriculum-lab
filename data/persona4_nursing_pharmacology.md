# persona4_nursing_pharmacology.pdf — PLACEHOLDER

**Replace this `.md` with the actual `.pdf` when sourced.**

## Requirements

| Field | Spec |
|---|---|
| Persona | 4 — Nursing (Prof. Diane Okafor, *NUR 320: Acute Care Pharmacology*) |
| Subject matter | Pharmacology chapter — a drug class (cardiac, respiratory, antimicrobial) with dosing, mechanism, adverse effects |
| Length | 15–25 pages |
| Reading level | BSN student / pre-NCLEX |
| Must contain | Actual drug names, dosing ranges, contraindications, calculation examples |

## Why this is the second demo-ready persona

Persona 4 shares clinical-demo potency with Persona 1. **Patient-safety framing makes the grounding case in 10 seconds**: "Imagine the AI invented a dosage range. Now imagine grounding prevents that." Powerful for nursing AND for any health-adjacent attendee.

## Suggested sourcing

- **OpenStax "Pharmacology for Nurses"** (CC-BY)
- **LibreTexts Medicine — Pharmacology**
- **WHO Model Formulary** (open access)
- **NCBI Bookshelf** — open pharmacology textbooks

## Demo questions the document should answer well

1. *"What are the key teaching points about this drug class?"*
2. *"Generate 5 med-calc practice problems based on the dosing information here."*
3. *"What are the highest-priority adverse effects students need to know for NCLEX?"*

## Quality check

Before staging:
- [ ] Loads in `PyPDFLoader` cleanly (drug tables sometimes break — verify)
- [ ] Grounded answers preserve exact dosing numbers from source
- [ ] Vanilla LLM may hallucinate dose ranges — **this is the key demo moment for the safety framing**
- [ ] Generated practice problems use only drugs/doses present in the source
