# Faculty AI Seminar — Curriculum Embedding Lab

**Embed AI in Your Course** — the seminar's afternoon lab (1:30–3:00 PM).

This is **not** a technical lab. There's some Python, but you're not learning to code. You're using a working AI tool to figure out exactly where AI fits in *your* course — and where it doesn't.

By 3:00 PM you walk out with:
1. A working AI tool tailored to your persona's vision
2. A written curriculum plan (course, week, assignment, what AI does, what you still do)
3. An explicit boundary for where AI does NOT belong in your teaching
4. A dated Monday morning commitment to one specific action

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
├── curriculum-embedding-lab.ipynb     ← the lab notebook
├── data/                              ← 6 sample PDFs (one per persona)
│   ├── README.md
│   ├── persona1_dentistry_perio_case.pdf
│   ├── persona2_cs_data_structures.pdf
│   └── ... (4 more)
├── mlu_utils/
│   └── embeddings.py                  ← Bedrock embeddings helper
└── instructor/                        ← run-of-show docs (not for participants)
```

## What this lab is NOT

- **Not a technical deep-dive on RAG, vector stores, or LangChain.** That's the standalone post-seminar lab — link in your seminar welcome email.
- **Not a coding tutorial.** You'll see ~5 cells of Python; you don't need to understand them. The writing cells matter more.
- **Not a sales pitch for AI.** Part 4 explicitly asks you to articulate where AI does NOT belong in your teaching. That's intentional.

## Troubleshooting

| Issue | Fix |
|---|---|
| `AccessDeniedException` invoking model | Bedrock model access not enabled — ask your instructor |
| Embedding cell hangs > 90 sec | Source PDF is too large — ask your instructor to swap to a smaller persona sample |
| `No such file or directory` for PDF | Wrong persona number set in Part 0, or sample PDF not yet staged — ask your instructor |
| Kernel disconnected | Restart kernel and re-run from Part 1 |

## After the seminar

Your downloaded artifact (`my_curriculum_plan_*.md`) is yours. The two best things to do with it Monday morning:

1. **Email it to yourself** with subject `Monday morning AI commitment`. Calendar reminders get ignored; emails do not.
2. **Tell one colleague** what you committed to. Social accountability is the strongest commitment device available.

If you want to keep building AI tools for your course beyond what you made today, the standalone post-seminar lab (RAG with SageMaker Studio) shows you how to extend the technical side — multi-document tutors, conversational memory, custom assessment generators, agentic versions. Link in your welcome email.
