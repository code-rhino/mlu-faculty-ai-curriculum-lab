# persona3_english_victorian_essay.pdf — PLACEHOLDER

**Replace this `.md` with the actual `.pdf` when sourced.**

## Requirements

| Field | Spec |
|---|---|
| Persona | 3 — English Literature (Dr. Sarah Whitman, *Victorian Literature & Empire*) |
| Subject matter | Victorian-era primary source — essay, short story, autobiography excerpt, or lecture text |
| Length | 10–20 pages |
| Reading level | Upper-division undergraduate humanities |
| Must contain | Substantive prose with thematic complexity — empire, race, gender, class, or industrialization |

## Why this persona is high-stakes

Persona 3 is the **AI-skeptic** in the room — concerned AI undermines critical thinking. The demo MUST show that grounding preserves the close-reading discipline, not replaces it. A weak sample here loses the humanities half of the audience.

## Suggested sourcing (Project Gutenberg — public domain)

- **Mary Seacole** — *Wonderful Adventures of Mrs. Seacole in Many Lands* (excerpt)
- **Frederick Douglass** — Speeches or autobiography excerpts
- **Thomas Carlyle** — Essays on history and empire
- **Oscar Wilde** — *The Soul of Man Under Socialism* or similar essay
- **Charles Dickens** — Essays from *Household Words*
- **Olaudah Equiano** — *The Interesting Narrative* (excerpt)

## Demo questions the document should answer well

1. *"What are the central themes a student should engage with in this text?"*
2. *"Generate discussion prompts that ask about authorial choice, not summary."*
3. *"Create a rubric for assessing close-reading of this passage."*

## Quality check

Before staging:
- [ ] Loads in `PyPDFLoader` (Gutenberg PDFs are usually clean)
- [ ] AI grounded responses cite specific passages, not generic Victorian-era summary
- [ ] Vanilla LLM gives plausible-sounding but generic answers, demonstrating the value of grounding
- [ ] Discussion prompts generated push toward analysis, not plot recap
