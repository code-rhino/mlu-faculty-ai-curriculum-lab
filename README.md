# Faculty AI Seminar — Curriculum Embedding Lab

**Embed AI in Your Course** — the seminar's afternoon lab (1:30–3:00 PM).

This is **not** a technical lab. There's some Python, but you're not learning to code. You're using a working AI tool to figure out exactly where AI fits in *your* course — and where it doesn't.

By 3:00 PM you walk out with:
1. A working AI tool tailored to your persona's vision
2. A written curriculum plan (course, week, assignment, what AI does, what you still do)
3. An explicit boundary for where AI does NOT belong in your teaching
4. A dated Monday morning commitment to one specific action

## Two notebooks in this repo

| Notebook | Audience | Purpose |
|---|---|---|
| **`curriculum-embedding-lab.ipynb`** | Faculty | Decide where AI fits in *your course* — the seminar's afternoon lab (below) |
| **`study-mastery-lab.ipynb`** | Students | A grounded study tool you can hand to students — quiz themselves, get Socratic hints, and check their understanding against their own course material. See [For students](#for-students-the-study--mastery-partner-lab). |

Both run in the same SageMaker Studio + Bedrock environment and share the same `mlu_utils/` helpers. Everything below describes the faculty lab unless noted.

## Quick start (in SageMaker Studio)

1. **Open SageMaker Studio** in JupyterLab mode (URL provided by your seminar instructor)
2. **Clone this repo** — Git icon in the sidebar → **Clone a Repository** → paste this repo's URL
3. **Open `curriculum-embedding-lab.ipynb`**
4. **Run cells top to bottom** — the notebook walks you through Parts 0 through 7
5. **Don't skip the writing cells** — they matter as much as the code cells

## How this lab is different from a normal coding lab

Two kinds of cells:

- **Watch-along code cells** (Part 1, parts of Part 2) — instructor runs these; no edits needed
- **🟢 EDIT ME cells** — you fill in values: your persona, your course, your commitment

A blank reflection cell means a missing plan. **Don't leave them blank.**

## The six personas

| # | Persona | Field | Tool you build |
|---|---|---|---|
| 1 | Dr. Maya Patel | Dentistry — Periodontics | Case Study Coach (3-level patient vignettes) |
| 2 | Prof. James Chen | Computer Science — Data Structures | Code Critique Generator (Socratic, no-answer) |
| 3 | Dr. Sarah Whitman | English Literature — Victorian Lit | Primary Source Companion (no plot-summary prompts) |
| 4 | Prof. Diane Okafor | Nursing — Pharmacology | Med-Calc Drill (dosing problems with safety red-flags) |
| 5 | Dr. Marcus Reyes | Business — Leadership MBA | Stakeholder Roleplay (AI plays CFO/CMO from the case) |
| 6 | Dr. Lena Hoffmann | Biology — Cell Biology Lab | Pre-Lab Knowledge Gate (quiz students must pass before lab) |

You picked your persona at registration. The notebook defaults to Persona 1; change it in the second cell.

## What you need

- AWS account with **Amazon Bedrock** model access for:
  - `amazon.nova-lite-v1:0`
  - `amazon.nova-2-multimodal-embeddings-v1:0`
- **SageMaker Studio** with a Python 3 (Data Science) kernel, `ml.t3.medium` or larger
- Region: `us-east-1`

Your seminar instructor handled all of this. If you have trouble, ask them — don't troubleshoot AWS during the lab.

## What's in this repo

```
mlu-faculty-ai-curriculum-lab/
├── README.md                          ← you are here
├── requirements.txt                   ← Python packages (pre-pinned)
├── curriculum-embedding-lab.ipynb     ← faculty lab notebook
├── study-mastery-lab.ipynb            ← student lab notebook (study tool)
├── data/                              ← 6 sample PDFs (one per persona)
│   ├── README.md
│   ├── persona1_dentistry_perio_case.pdf
│   ├── persona2_cs_data_structures.pdf
│   └── ... (4 more)
├── mlu_utils/
│   ├── embeddings.py                  ← Bedrock embeddings helper
│   └── study_tools.py                 ← study-mode prompts (student lab)
└── instructor/                        ← run-of-show docs (not for participants)
```

## What this lab is NOT

- **Not a technical deep-dive on RAG, vector stores, or LangChain.** That's the standalone post-seminar lab — link in your seminar welcome email.
- **Not a coding tutorial.** You'll see ~5 cells of Python; you don't need to understand them. The writing cells matter more.
- **Not a sales pitch for AI.** Part 4 explicitly asks you to articulate where AI does NOT belong in your teaching. That's intentional.

## For students: the Study &amp; Mastery Partner lab

`study-mastery-lab.ipynb` is a **student-facing** companion. It's a grounded study tool — students point it at their own course material (a reading, lecture notes, a textbook chapter) and use three modes:

- **Quiz Me** — a practice quiz generated from the material, with a hidden answer key to self-test against.
- **Socratic Hint** — paste a problem you're stuck on; it gives the *next question to ask yourself*, never the answer.
- **Explain-Back** — write a concept in your own words and have it checked against the source, so you see your gaps.

It ships with a sample chapter so it runs immediately; students swap in their own PDF by dropping a file into `data/` and changing one line (`SOURCE_PDF`). It ends with an academic-integrity reflection — **use AI to study, not to do the thinking you're graded on** — and a take-home study plan.

**What this lab is NOT:** not a way to get answers to graded work (Socratic and Explain-Back modes deliberately withhold answers), and not a coding tutorial.

Same requirements as the faculty lab (Bedrock access for `amazon.nova-lite-v1:0` + `amazon.nova-2-multimodal-embeddings-v1:0`, SageMaker Studio, `us-east-1`). This lab is **self-paced** and can be run on its own, after or independent of the seminar.

## Troubleshooting

| Issue | Fix |
|---|---|
| `AccessDeniedException` invoking model | Bedrock model access not enabled — ask your instructor |
| Embedding cell hangs > 90 sec | Source PDF is too large — ask your instructor to swap to a smaller persona sample |
| `No such file or directory` for PDF | Wrong persona number set in Part 0, or sample PDF not yet staged — ask your instructor |
| Kernel disconnected | Restart kernel and re-run from Part 1 |
| _(student lab)_ `No such file or directory` for your PDF | Your file isn't in `data/`, or `SOURCE_PDF` doesn't match its name — check the file browser on the left |
| _(student lab)_ Loads 0 pages / garbled text | Your PDF is a scan/image, not text — `PyPDFLoader` can't read it. Use a text-based PDF |
| _(student lab)_ Socratic Hint gave away the answer | A known limitation of smaller models — re-run the cell; don't trust a leaked answer blindly |

## After the seminar

Your downloaded artifact (`my_curriculum_plan_*.md`) is yours. The two best things to do with it Monday morning:

1. **Email it to yourself** with subject `Monday morning AI commitment`. Calendar reminders get ignored; emails do not.
2. **Tell one colleague** what you committed to. Social accountability is the strongest commitment device available.

If you want to keep building AI tools for your course beyond what you made today, the standalone post-seminar lab (RAG with SageMaker Studio) shows you how to extend the technical side — multi-document tutors, conversational memory, custom assessment generators, agentic versions. Link in your welcome email.
