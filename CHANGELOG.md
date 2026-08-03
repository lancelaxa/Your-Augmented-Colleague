# CHANGELOG.md

> ⚠️ Teaching repository. See [disclaimer](README.md#-disclaimer).

Chronological record of changes to operational guidelines, templates and learning material.

---

## Why this file exists

Three reasons:

1. **Accountability.** During an internal or client audit, "when did this rule change, and
   who approved it?" must have an answer.
2. **Communication.** People need to know when a procedure they rely on has moved.
3. **Learning.** A pattern of changes in one area usually indicates the original was wrong,
   which is worth noticing.

**Git already records every change.** This file is the *human-readable* layer on top —
grouping raw commits into meaningful changes with their reasons. Use both: this file for
what and why, Git history for exactly what changed.

---

## How to update

Whenever a PR is merged that changes operational content:

1. Add an entry under `[Unreleased]`
2. Categorise it (see below)
3. **State the reason, not just the change**
4. Link the PR or issue

Entries move from `[Unreleased]` into a dated version at each review cycle.

### Categories

| Tag | Meaning |
|-----|---------|
| `Added` | New content |
| `Changed` | Modified existing content |
| `Deprecated` | Still present, being phased out |
| `Removed` | Deleted |
| `Fixed` | Corrections |
| `Security` | Compliance or data protection changes |

**`Security` entries require DPO review before merge.**

---

## [Unreleased]

### Added

- `slides/index.html` — presentation deck, "Beyond the Prompt". 21 slides for a
  non-technical audience that already uses AI at work. Self-contained single file:
  keyboard navigation, on-screen speaker notes (`N`), print/PDF export, light and dark
  themes, no external dependencies.
- `slides/SPEAKER-NOTES.md` — talking points for all 21 slides, generated from the deck
  so the two cannot drift apart.

### Changed

- `README.md`, `INDEX.md` — added deck and speaker-notes links.

### Deck design

Slides carry a headline and one idea each — about 55 words on screen on average — and act
as a backdrop rather than a script. All explanatory detail sits in the speaker notes, at
roughly three words of presenter script for every word on screen. The notes include the
analogies to use, questions to put to the room, jargon to expand aloud, and the objections
to pre-empt.

### Notes on the deck's reading level

Written for people with no technical background who already use AI day to day. Every
abstract idea is carried by a worked recruitment, business development or operations
example rather than stated in the abstract; jargon is expanded on first use ("tender",
"RFP", "GeBIZ"); and each content slide states an explicit takeaway. Graph engineering is
introduced through an existing approval process rather than through framework
terminology.

---

## [1.0.0] — 2026-08-03

Initial publication of the repository.

### Added — Learning track

- `learn/00-START-HERE.md` — orientation, the four rungs, ground rules
- `learn/01-PROMPT-ENGINEERING.md` — prompt anatomy, techniques, the data fence
- `learn/02-CONTEXT-ENGINEERING.md` — Write/Select/Compress/Isolate, context rot
- `learn/03-LOOP-ENGINEERING.md` — **deep dive**: origin (June 2026), the four parts,
  Osmani's six components, the verifier strength ladder, compounding reliability
  mathematics, the six failure modes, the maturity ladder, build guide, metrics
- `learn/04-GRAPH-ENGINEERING.md` — **deep dive**: state/nodes/edges, checkpointing and
  time travel, human-in-the-loop, the five workflow patterns, supervisor vs swarm, worked
  milestone sign-off graph
- `learn/05-THE-STACK-COMPARED.md` — decision tables, decision tree, anti-patterns,
  readiness checklist
- `learn/06-EVIDENCE-PACK.md` — every statistic with sources, quotable definitions,
  suggested slide order, and guidance on responsible use of the figures
- `learn/07-GITHUB-FOR-NON-CODERS.md` — Git and GitHub in operations language

### Added — Governance

- `compliance/COMPLIANCE.md` — four-tier data classification, the NRIC rule, approved-tool
  criteria, redaction procedure, rules for AI-assisted decisions about people, PDPC
  generative-AI guidance summary, IMDA framework alignment
- `compliance/data-governance.md` — systems map, retention schedule, access control,
  repository rules including *Git never forgets*, AI-specific governance, vendor management,
  incident response
- `WORKFLOW.md` — SOP-01 vendor approval · SOP-02 milestone sign-off · SOP-03 deliverable
  handover · SOP-04 AI-assisted document production · SOP-05 changing an SOP

### Added — Playbooks and templates

- `playbooks/RECRUITMENT.md` — 8-stage pipeline, screening controls, anonymised evaluation
  criteria, onboarding checklist, automation priorities
- `playbooks/BIZ-DEV.md` — tender pipeline, qualification scorecard, bid/no-bid authority
  matrix, compliance matrix method, pricing structure
- `projects-imda/IMDA-DELIVERABLES.md` — *(demo)* milestone tracker, acceptance-criteria
  guidance, issue cross-referencing conventions
- `projects-imda/audit-logs.md` — *(demo)* audit trail, AI usage log, incident log with a
  worked root-cause example
- `templates/rfp-response-v1.md` — full response structure with compliance matrix and
  pre-submission verification
- `templates/candidate-eval-v1.md` — anonymised scoring sheet with fairness checklist and
  worked example

### Added — Hub files

- `README.md` — landing page *(expanded from the initial stub, tagline retained)*
- `INDEX.md` — master file map, find-by-question and find-by-role navigation
- `PROMPTS.md` — reusable prompt blocks plus 8 working prompts
- `CHANGELOG.md` — this file
- `.github/ISSUE_TEMPLATE/` — four standardised intake forms
- `.github/pull_request_template.md` — PR checklist including a PII check

### Notes on sourcing

Learning-track content is built on publicly available material published between 2024 and
mid-2026, principally the loop engineering essays of **June 2026**, published LangGraph
graph-engineering practice, and industry reliability analyses.

Compliance content summarises publicly available Singapore regulatory guidance —
**PDPC Advisory Guidelines on Use of Personal Data in Generative AI (20 July 2026)**, the
PDPC NRIC advisory guidelines, the **PDPC–CSA Joint Advisory (June 2025)**, IMDA's Model AI
Governance Framework for Generative AI, and the AI Verify testing framework.

> ⚠️ **All sources are secondary.** Figures and regulatory statements must be verified at
> source before external or operational use. See
> [how to use these numbers responsibly](learn/06-EVIDENCE-PACK.md#-how-to-use-these-numbers-responsibly).
> Compliance content is **not legal advice** and requires Legal/DPO review.

---

## Planned

Not yet built. Contributions welcome.

| Item | Rationale |
|------|-----------|
| Automated PII detection script | Highest-value first automation — see [P-02](PROMPTS.md#p-02--redaction-verification) |
| Worked loop example with real tooling | Move the maturity ladder from theory to practice |
| Team-specific prompt collections | As usage patterns emerge |
| Quarterly statistics refresh | The field moves fast; figures date quickly |
| Real approved-tool list | Blocked on IT/Legal input |
| Populated role assignments | Blocked on HQ Ops input |

---

## Review schedule

| Review | Frequency | Owner |
|--------|-----------|-------|
| SOPs | Quarterly | Process owners |
| Compliance content | Quarterly | DPO |
| Learning-track statistics | Semi-annually | HQ Ops |
| Full review with Legal | Annually | DPO |

---

*Format loosely follows [Keep a Changelog](https://keepachangelog.com/).*
