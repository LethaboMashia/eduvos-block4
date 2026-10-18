# Eduvos Block 4 — Coursework Repository

![Status](https://img.shields.io/badge/status-in--progress-orange)
![Institution](https://img.shields.io/badge/Eduvos-Midrand%20Campus-blue)
![Program](https://img.shields.io/badge/BSc-Information%20Technology-informational)

Block 4 coursework for my BSc in Information Technology at Eduvos, Midrand Campus. This repository tracks weekly deliverables, applied analyses, and portfolio-grade work across three concurrent modules, approached less as "homework to submit" and more as a working record of how I think through interface design, algorithmic problem-solving, and data modelling — the kind of thinking a software engineering role actually demands day-to-day.

## Why This Repo Exists

Most coursework repositories are checklists: a file per week, minimal explanation, closed the moment it's marked. I've structured this one differently — every submission is written as a standalone case study with reasoning shown, not just conclusions stated, because the ability to *explain why* a design or implementation decision is correct is the actual skill being assessed, both here and in a real engineering role. If you're a recruiter or reviewer skimming this, the `portfolio-ux-teardown` folder is the best single entry point.

## Modules Covered

### 🎯 Interaction & Usability Engineering (ITUEA)
Theory and applied analysis of how humans interact with software — conceptual models, affordance theory (perceived vs. real), interaction paradigms, cognitive load, and usability heuristics — tested against real, currently-shipping consumer products rather than hypothetical examples.

### 🧮 Data Structures & Algorithms in Python
Implementation and complexity analysis of core data structures and algorithms — correctness, Big-O reasoning, and problem-solving approach, not just working code.

### 🗄️ Database Systems
Schema design, normalization (up to 3NF and beyond where relevant), and SQL — from raw, messy table structures through to properly normalized relational models.

## Repository Structure

| Folder | Module | What's Inside |
|---|---|---|
| [`week01-interaction-design`](./week01-interaction-design) | ITUEA | Full interaction design breakdown of Spotify — conceptual model, two principles demonstrated well (feedback, visibility), one principle violated (affordance), and a mechanism-based redesign recommendation |
| [`week02-conceptualising-interaction`](./week02-conceptualising-interaction) | ITUEA | WhatsApp analyzed through affordance theory (including a confirmed perceived-vs-real mismatch in the attachment menu), interface metaphors, and interaction paradigms (direct manipulation vs. natural language) |
| [`portfolio-ux-teardown`](./portfolio-ux-teardown) | ITUEA | Standalone portfolio case study on the Capitec Bank app — conceptual model, three affordances with verdicts, cognitive load analysis (including a slip-type error), and a redesign recommendation with reasoning tied back to visual-search theory |

Each file follows a consistent structure: identify the concept, show concrete evidence from the live product, and where something fails, explain *why* the proposed fix addresses that specific failure mechanism rather than just suggesting a generic improvement.

## Approach

I treat each deliverable the way I'd treat a design review at work:
1. **State the claim** — which principle, model, or paradigm applies
2. **Show the evidence** — a specific, observable moment in the actual interface, not a vague generalization
3. **Diagnose the mechanism** — *why* it works or fails, grounded in the underlying theory (recognition vs. recall, pre-attentive visual processing, slip vs. mistake, etc.)
4. **Propose a fix proportional to the problem** — where something's broken, the fix should be the smallest change that addresses the actual mechanism, not a redesign for its own sake

## Tech & Tools

- **Git / GitHub** for version control and submission tracking
- **Markdown** for all written analysis — readable in-browser with no extra tooling required
- **VS Code** as the primary editor across all modules

## About Me

I'm an IT student with a practical, product-oriented lens — alongside my studies I run **BAS TECH** (Bohlale Automated Services Technology), an AI-powered automation and marketing agency based in Gauteng, South Africa, and I'm also building an independent AI audit and automation consulting practice diagnosing operational inefficiencies for SA SMEs. That business context shapes how I approach this coursework: usability and data design aren't abstract exercises to me, they're the difference between a client tool that gets adopted and one that doesn't.

Open to internship and junior software engineering opportunities — feel free to reach out via GitHub.

---
*Lethabo Mashia · EDUV5085090 · BSc Information Technology, Eduvos Midrand Campus*
*Last updated: October 2026*