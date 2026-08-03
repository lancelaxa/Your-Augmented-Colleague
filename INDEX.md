# INDEX.md — Master File Map

> ⚠️ Teaching repository. All operational content is illustrative with fictional data.
> See [disclaimer](README.md#-disclaimer).

**Find any document in seconds.** If you cannot, that is a bug — open an issue.

---

## 🔍 Find it by question

| "I need to…" | Go to |
|---|---|
| Understand what this repo is | [README.md](README.md) |
| Start learning AI properly | [learn/00-START-HERE.md](learn/00-START-HERE.md) |
| Know what I can/can't put into AI | [compliance/COMPLIANCE.md](compliance/COMPLIANCE.md) |
| Find a proven prompt | [PROMPTS.md](PROMPTS.md) |
| Check if a CV is safe to process | [PROMPTS.md → P-02](PROMPTS.md#p-02--redaction-verification) |
| Screen a candidate | [playbooks/RECRUITMENT.md](playbooks/RECRUITMENT.md) + [candidate-eval-v1](templates/candidate-eval-v1.md) |
| Respond to a tender | [playbooks/BIZ-DEV.md](playbooks/BIZ-DEV.md) + [rfp-response-v1](templates/rfp-response-v1.md) |
| Approve a vendor | [WORKFLOW.md → SOP-01](WORKFLOW.md#sop-01--vendor--subcontractor-approval) |
| Sign off a milestone | [WORKFLOW.md → SOP-02](WORKFLOW.md#sop-02--milestone-sign-off) |
| Hand over a deliverable | [WORKFLOW.md → SOP-03](WORKFLOW.md#sop-03--deliverable-handover) |
| Use AI on a client document | [WORKFLOW.md → SOP-04](WORKFLOW.md#sop-04--ai-assisted-document-production) |
| Change a procedure | [WORKFLOW.md → SOP-05](WORKFLOW.md#sop-05--changing-an-sop) |
| Present AI strategy to leadership | [learn/06-EVIDENCE-PACK.md](learn/06-EVIDENCE-PACK.md) |
| Report a data incident | [COMPLIANCE.md §4](compliance/COMPLIANCE.md#4-the-nric-rule--read-this-twice) + [data-governance §8](compliance/data-governance.md#8-incident-response) |
| Learn GitHub from zero | [learn/07-GITHUB-FOR-NON-CODERS.md](learn/07-GITHUB-FOR-NON-CODERS.md) |
| Decide whether to automate something | [learn/05-THE-STACK-COMPARED.md](learn/05-THE-STACK-COMPARED.md#the-decision-tree) |
| See what changed recently | [CHANGELOG.md](CHANGELOG.md) |

---

## 📁 By folder

### `/` — Root

| File | Purpose | Owner |
|------|---------|-------|
| [README.md](README.md) | Landing page, orientation | HQ Ops |
| [INDEX.md](INDEX.md) | This file | HQ Ops |
| [PROMPTS.md](PROMPTS.md) | Shared AI prompt library | All |
| [WORKFLOW.md](WORKFLOW.md) | SOPs with approval gates | HQ Ops |
| [CHANGELOG.md](CHANGELOG.md) | Change audit trail | HQ Ops |

### `/learn` — The AI learning track

| File | Purpose | Read time |
|------|---------|-----------|
| [00-START-HERE.md](learn/00-START-HERE.md) | Orientation, the four rungs | 5 min |
| [01-PROMPT-ENGINEERING.md](learn/01-PROMPT-ENGINEERING.md) | Rung 1 — the single message | 20 min |
| [02-CONTEXT-ENGINEERING.md](learn/02-CONTEXT-ENGINEERING.md) | Rung 2 — the whole window | 20 min |
| [03-LOOP-ENGINEERING.md](learn/03-LOOP-ENGINEERING.md) 🔍 | Rung 3 — **deep dive** | 45 min |
| [04-GRAPH-ENGINEERING.md](learn/04-GRAPH-ENGINEERING.md) 🔍 | Rung 4 — **deep dive** | 45 min |
| [05-THE-STACK-COMPARED.md](learn/05-THE-STACK-COMPARED.md) | Decision tables | 15 min |
| [06-EVIDENCE-PACK.md](learn/06-EVIDENCE-PACK.md) 📊 | **All data, sourced** | Reference |
| [07-GITHUB-FOR-NON-CODERS.md](learn/07-GITHUB-FOR-NON-CODERS.md) | Git in ops language | 30 min |

### `/compliance` — Governance

| File | Purpose | Owner |
|------|---------|-------|
| [COMPLIANCE.md](compliance/COMPLIANCE.md) | Data classification, NRIC rule, approved tools, redaction | DPO |
| [data-governance.md](compliance/data-governance.md) | Systems map, retention, access, incidents, vendors | DPO |

### `/playbooks` — Team procedures

| File | Purpose | Owner |
|------|---------|-------|
| [RECRUITMENT.md](playbooks/RECRUITMENT.md) | 8-stage hiring pipeline | Recruitment Lead |
| [BIZ-DEV.md](playbooks/BIZ-DEV.md) | Tender and commercial pipeline | BD Director |

### `/projects-imda` — Demo project *(fictional data)*

| File | Purpose | Owner |
|------|---------|-------|
| [IMDA-DELIVERABLES.md](projects-imda/IMDA-DELIVERABLES.md) | Milestone tracker, acceptance criteria | HQ Ops Lead |
| [audit-logs.md](projects-imda/audit-logs.md) | Audit trail, AI usage log, incidents | HQ Ops Lead |

### `/templates` — Reusable blocks

| File | Purpose | Version |
|------|---------|---------|
| [rfp-response-v1.md](templates/rfp-response-v1.md) | RFP response + compliance matrix | v1.0 |
| [candidate-eval-v1.md](templates/candidate-eval-v1.md) | Anonymised scoring sheet | v1.0 |

### `/.github/ISSUE_TEMPLATE` — Intake forms

| Template | Use for |
|----------|---------|
| `candidate-intake.yml` | New requisition / headcount request |
| `bd-opportunity.yml` | New tender or commercial opportunity |
| `milestone-tracking.yml` | Project milestone tracking |
| `sop-change.yml` | Proposing a procedure change |

---

## 🎯 By role

### Recruitment consultant
1. [00-START-HERE](learn/00-START-HERE.md) → [COMPLIANCE](compliance/COMPLIANCE.md)
2. [RECRUITMENT.md](playbooks/RECRUITMENT.md)
3. [candidate-eval-v1](templates/candidate-eval-v1.md)
4. [PROMPTS P-01, P-02, P-08](PROMPTS.md)

### Business developer
1. [00-START-HERE](learn/00-START-HERE.md) → [COMPLIANCE](compliance/COMPLIANCE.md)
2. [BIZ-DEV.md](playbooks/BIZ-DEV.md)
3. [rfp-response-v1](templates/rfp-response-v1.md)
4. [PROMPTS P-03, P-04, P-06](PROMPTS.md)

### HQ operations
1. The full [learn track](learn/00-START-HERE.md)
2. [WORKFLOW.md](WORKFLOW.md) — all SOPs
3. [data-governance.md](compliance/data-governance.md)
4. [audit-logs.md](projects-imda/audit-logs.md)

### Leadership
1. [Evidence pack](learn/06-EVIDENCE-PACK.md) — the data
2. [Stack compared](learn/05-THE-STACK-COMPARED.md) — the decision framework
3. [Maturity ladder](learn/03-LOOP-ENGINEERING.md#9-the-loop-maturity-ladder) — where we are
4. [COMPLIANCE §2](compliance/COMPLIANCE.md#2-why-this-is-stricter-than-you-might-expect) — the commercial angle

---

## 🏷️ Data classification map

| Tier | Where it lives |
|------|----------------|
| 🟢 **PUBLIC** | This repository |
| 🔵 **INTERNAL** | Private ops repo · SOPs, prompt library, training |
| 🟠 **CONFIDENTIAL** | Private restricted repo · pricing, bid strategy, client terms |
| 🔴 **RESTRICTED** | **ATS / systems of record only — never any repository** |

---

## 🔑 Key concepts, and where they're explained

| Concept | Where |
|---------|-------|
| The four rungs | [00-START-HERE](learn/00-START-HERE.md#the-four-rungs) |
| Write · Select · Compress · Isolate | [02](learn/02-CONTEXT-ENGINEERING.md#the-four-moves-write-select-compress-isolate) |
| Context rot | [02](learn/02-CONTEXT-ENGINEERING.md#the-counter-intuitive-part-more-context-makes-it-worse) |
| Trigger · topology · verifier · stop rule | [03](learn/03-LOOP-ENGINEERING.md#3-anatomy-of-a-loop-the-four-parts) |
| The verifier strength ladder | [03](learn/03-LOOP-ENGINEERING.md#the-verifier-strength-ladder) |
| Compounding reliability (`p^N`) | [03](learn/03-LOOP-ENGINEERING.md#61-reliability-compounds-downward) |
| The six agent failure modes | [03](learn/03-LOOP-ENGINEERING.md#7-the-six-failure-modes) |
| The loop maturity ladder | [03](learn/03-LOOP-ENGINEERING.md#9-the-loop-maturity-ladder) |
| State · nodes · edges | [04](learn/04-GRAPH-ENGINEERING.md#2-the-three-primitives-state-nodes-edges) |
| Checkpointing & time travel | [04](learn/04-GRAPH-ENGINEERING.md#4-checkpointing-time-travel-and-recovery) |
| `interrupt_before` vs `interrupt_after` | [04](learn/04-GRAPH-ENGINEERING.md#5-human-in-the-loop-as-a-first-class-citizen) |
| The five workflow patterns | [04](learn/04-GRAPH-ENGINEERING.md#6-the-pattern-catalogue) |
| Supervisor vs swarm | [04](learn/04-GRAPH-ENGINEERING.md#7-supervisor-vs-swarm--and-what-survives-production) |
| Data classification tiers | [COMPLIANCE §3](compliance/COMPLIANCE.md#3-data-classification) |
| The NRIC rule | [COMPLIANCE §4](compliance/COMPLIANCE.md#4-the-nric-rule--read-this-twice) |

---

## 🔧 Maintenance

| Task | Frequency | Owner |
|------|-----------|-------|
| Update this index when files are added | On change | Whoever adds the file |
| Review all SOPs | Quarterly | Process owners |
| Review compliance content against current guidance | Quarterly | DPO |
| Full review with Legal | Annually | DPO |
| Refresh learn-track statistics | Semi-annually | HQ Ops |

> The learn track cites a fast-moving field — loop engineering was named in **June 2026**.
> Treat anything over six months old as needing a re-check.

---

*See [CHANGELOG.md](CHANGELOG.md) for change history.*
