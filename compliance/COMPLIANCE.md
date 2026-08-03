# COMPLIANCE.md — Data Classification & AI Usage Rules

> ## ⚠️ TEACHING DOCUMENT
> This is an **illustrative template** in a public teaching repository. It is **not** CGP's
> operative compliance policy and has **no legal force**. Thresholds, role names and
> procedures are examples to be adapted. **This is not legal advice** — all of it must be
> reviewed and approved by Legal and the Data Protection Officer before any real use.
> Statutory references must be verified at source; see
> [learn/06-EVIDENCE-PACK.md §F](../learn/06-EVIDENCE-PACK.md#f-singapore-regulatory-context).

---

## 1. The one-page version

If you read nothing else:

### 🚫 Never put these into any AI tool

- **NRIC, FIN, work permit or passport numbers** — no exceptions, no partial digits
- **Candidate phone numbers, personal emails, home addresses**
- **Date of birth** (year alone is usually acceptable if genuinely needed)
- **Bank details, salary tied to a named individual**
- **Medical, disability or health information**
- **Client-confidential commercial terms** in a consumer AI account
- **Anything marked RESTRICTED** (see §3)

### ✅ Always

- **Anonymise before the prompt**, not after the output
- Use **approved tools only** (§5) for anything above PUBLIC
- **Human review** before any AI-assisted output leaves CGP
- **Log it** if it informed a decision about a person or a bid

### The rule that resolves most questions

> **Would you be comfortable if this exact text appeared in a regulator's file, attributed
> to CGP, with the client's name attached?**
>
> If not, it does not go into an AI tool.

---

## 2. Why this is stricter than you might expect

Three reasons this matters more for CGP than for a typical firm:

1. **We handle candidate personal data at volume.** Recruitment is one of the most
   PII-dense activities that exists. A CV is a dossier.
2. **We deliver into the public sector.** Government-linked work carries heightened
   scrutiny, and AI governance is moving *into procurement standards* — AI Verify and ISAGO
   are being embedded into public-sector procurement requirements. Weak AI governance is
   becoming a **commercial disqualifier**, not just a compliance risk.
3. **The penalties are material.** PDPA financial penalties run up to **S$1 million**, or
   **10% of annual turnover** in Singapore for organisations with turnover above S$10m.

> **Reframe worth internalising:** demonstrable AI governance is not overhead. It is
> increasingly a **qualification to bid.**

---

## 3. Data classification

Four tiers. Every document and every prompt falls into one.

| Tier | Definition | Examples | AI tools | Repo |
|------|------------|----------|----------|------|
| 🟢 **PUBLIC** | Already public | Job ads, published tenders, our website copy, this repo | Any approved | Public OK |
| 🔵 **INTERNAL** | Ordinary business, not for outsiders | SOPs, templates, prompt library, training material | Approved tools | **Private only** |
| 🟠 **CONFIDENTIAL** | Commercially sensitive; damaging if leaked | Pricing, bid strategy, client terms, pipeline | Approved **enterprise** tools only, with approval | **Private, restricted** |
| 🔴 **RESTRICTED** | Personal data + regulated + contractual | CVs with identifiers, NRIC/FIN, salary by name, medical, security-cleared personnel | **🚫 NOT WITHOUT REDACTION** | 🚫 **Never in any repo** |

**RESTRICTED never enters a repository — public or private.** Repos are for *documents
about the work*, never for the personal data itself. That belongs in the ATS and approved
systems of record, with their access controls and retention schedules.

---

## 4. The NRIC rule — read this twice

The single highest-risk item in recruitment work.

### The legal position

Organisations are **generally prohibited** from collecting, using or disclosing an
individual's NRIC number (or a copy of the NRIC) **unless**:

- it is **required by law**; or
- it is **necessary to accurately establish or verify identity to a high degree of
  certainty**.

Additionally, per the **PDPC–CSA Joint Advisory (June 2025)**, NRIC numbers must **not** be
used as identity verification credentials — no NRIC as password, login ID or default
credential. Organisations must stop using NRIC for authentication by **31 December 2026**.

### The operating rule for AI tools

> **An NRIC never has a legitimate reason to be in a prompt. Ever.**

Screening, summarising, matching, ranking, drafting — none of these require an identity
number. If an NRIC is in your prompt, something has gone wrong upstream.

### Formats to strip

Singapore NRIC/FIN is a letter + 7 digits + a checksum letter:

```
S1234567D    T0123456A    F7654321X    G1234567L    M1234567K
```

Also strip: passport numbers, work permit numbers, phone numbers (`+65 XXXX XXXX`, 8-digit
local), personal email addresses, and residential addresses.

### If it happens anyway

1. **Stop.** Do not continue the conversation.
2. **Delete the conversation** where the tool allows it.
3. **Report within 24 hours** to your manager and the DPO.
4. **Log it** in [projects-imda/audit-logs.md](../projects-imda/audit-logs.md) (or the real
   incident register).
5. Do **not** quietly move on. An unreported near-miss is a repeat incident waiting to
   happen, and disclosure timelines are not yours to decide.

**Reporting a mistake is never itself a disciplinary matter. Concealing one is.**

---

## 5. Approved tools

> 📝 Placeholder — Legal/IT to complete with actual approved tooling.

| Tool | Max tier | Notes |
|------|----------|-------|
| _[Enterprise AI tool]_ | 🟠 CONFIDENTIAL | Enterprise agreement; no training on our data; SG/approved region |
| _[Consumer AI account]_ | 🟢 PUBLIC | **Personal accounts: PUBLIC data only** |
| _[Internal ATS]_ | 🔴 RESTRICTED | System of record; not an AI tool |

### What to check before any tool is approved

- [ ] Is there an **enterprise agreement**, or is this a consumer account?
- [ ] Is our data **used for model training**? (It must not be.)
- [ ] **Where is data processed and stored?** Cross-border transfer obligations apply.
- [ ] **Retention** — how long, and can we delete on request?
- [ ] Does it meet client/IMDA contractual security requirements?
- [ ] Are there **audit logs** of who submitted what?

**Personal ChatGPT/Claude/Gemini accounts are PUBLIC-tier only.** No client data, no
candidate data, no pricing. This is the most commonly broken rule in every organisation,
and it is broken with good intentions by people trying to be efficient.

---

## 6. The redaction procedure

**Redact before the prompt. Every time.**

### For a CV

| Remove | Replace with |
|--------|--------------|
| Full name | `Candidate A` |
| NRIC / FIN / passport | *(delete entirely — never tokenise)* |
| Phone, email, address | *(delete entirely)* |
| Date of birth | *(delete; use "8 years' experience" instead)* |
| Photograph | *(delete)* |
| Current employer, if identifying | `[Regional bank]`, `[Government agency]` |
| Referee details | *(delete)* |

**Keep:** skills, certifications, years of experience, sector history, education level,
achievements. Everything you actually screen on survives redaction — which is the point,
and also a useful reminder that identity data was never doing screening work anyway.

### The verification step

After redacting, before prompting, scan for:

- [ ] Any letter + 7 digits + letter pattern
- [ ] Any 8-digit number (SG phone)
- [ ] `@` symbols
- [ ] Full names, including in file names and headers/footers
- [ ] Identifying detail in free text — *"I led the team of 4 at [uniquely identifying
      project]"*

That last one is the one people miss. **Anonymisation is not just field removal**; a
sufficiently specific description re-identifies someone even with every field stripped.

> **Automate this check.** A regex-based PII detector is a ⭐⭐⭐⭐⭐ deterministic verifier
> (see [loop engineering §5](../learn/03-LOOP-ENGINEERING.md#5-the-verifier-problem--the-hard-part))
> and is the highest-value first automation this team could build — higher value than any
> drafting assistant.

---

## 7. AI-assisted decisions about people

Special care applies where AI touches hiring outcomes.

### Rules

1. **AI does not make hiring decisions.** It prepares, summarises and structures. A named
   human decides, and owns the decision.
2. **No protected characteristics.** Prompts must instruct the model to ignore age, race,
   religion, gender, nationality, marital or family status, disability. See the screening
   prompt in [PROMPTS.md](../PROMPTS.md).
3. **Same rubric for every candidate in a role.** Varying the prompt between candidates
   destroys comparability and is a fairness problem.
4. **Record that AI was used** in the assessment record.
5. **Be able to explain any rejection** without reference to AI output. If the only
   available explanation is "the tool scored them low," that is not a defensible decision.

### The bias trap

An AI summary of a CV is not neutral. It can amplify patterns in its training data, and it
will confidently produce a plausible-sounding rationale for a judgement it made on a
spurious basis. The mitigations: a **fixed written rubric**, **evidence quoted from the
CV** for every score, and **"No evidence" as a permitted answer** instead of a guess.

This is also precisely why the AI Verify framework pairs **technical testing** with
**process checks** — governance and documentation practices, not just model outputs.

---

## 8. Generative AI and personal data — the PDPC guidance

> Summary of the shape of the obligations. Verify at source; not legal advice.

The PDPC issued **Advisory Guidelines on Use of Personal Data in Generative AI** on
**20 July 2026**, covering three lifecycle phases: **development, deployment,
post-deployment.**

Two points with direct operational consequences:

**AI-Specific Notifications.** General notices — a privacy policy saying data may be used
for "new product development" — are **insufficient** to obtain consent for using personal
data in large-scale generative AI training or fine-tuning. Where consent is the basis,
notification must **expressly address AI model development**.

> **Consequence for CGP:** if any vendor or internal initiative proposes training or
> fine-tuning on candidate data, existing consent almost certainly does not cover it. Route
> to DPO before anything else happens.

**The publicly available exception.** Organisations may rely on it for data that is
genuinely publicly available — but must actually test whether the data is genuinely
publicly accessible and whether the use is reasonable in the circumstances. "It was on
LinkedIn" is not a blanket authorisation.

---

## 9. IMDA / public-sector delivery

Where we deliver into government programmes, additional expectations apply.

**IMDA's Model AI Governance Framework for Generative AI** addresses hallucination, bias,
intellectual property, content provenance, cybersecurity and systemic risk, with emphasis
on data quality, transparency, incident reporting, security, safety and testing, and
content provenance.

**AI Verify** combines **technical testing** with **process checks** against transparency,
explainability, fairness, safety and accountability.

These frameworks are **voluntary**, but are being embedded into **public-sector procurement
standards** — which converts them, in practice, into commercial requirements.

### What this means concretely

| Expectation | How we meet it |
|---|---|
| Transparency | Declare AI assistance in deliverables where material |
| Accountability | A named human owner for every AI-assisted output |
| Auditability | Versioned documents + PR approval history + [audit log](../projects-imda/audit-logs.md) |
| Data governance | This document + [data-governance.md](data-governance.md) |
| Incident reporting | §4 escalation path |
| Testing | Verification checklists in every playbook |

> **Note the convenient overlap:** an audit trail is exactly what
> [checkpointing](../learn/04-GRAPH-ENGINEERING.md#4-checkpointing-time-travel-and-recovery)
> produces as a by-product, and exactly what a **PR approval history** produces as a
> by-product. Good architecture and good governance want the same artefacts.

---

## 10. Roles

> 📝 Placeholder — populate with actual names.

| Role | Owns |
|------|------|
| **Data Protection Officer** | PDPA compliance, breach response, this policy |
| **HQ Operations Lead** | Workflow adherence, audit log |
| **Compliance Reviewer** | Sign-off on client-facing AI-assisted output |
| **Tool Owner (IT)** | Approved tool list, access, vendor due diligence |
| **Every employee** | Classifying correctly, redacting, reporting incidents |

---

## 11. Quick reference

| Situation | Answer |
|-----------|--------|
| Summarise a CV | ✅ **Redact first.** No name, NRIC, contact details |
| Paste a CV as received | 🚫 Never |
| Draft a job ad | ✅ Fine — PUBLIC |
| Summarise a published tender | ✅ Fine — PUBLIC |
| Draft our bid pricing | 🟠 Approved enterprise tool + approval |
| Use personal ChatGPT for client work | 🚫 No |
| Ask AI to rank candidates | ⚠️ Redacted + fixed rubric + human decides |
| Upload the client contract | 🚫 No |
| Draft a status report from internal notes | 🔵 Approved tool, redact names |
| Train a model on our CV database | 🚫 **Stop. DPO first.** Consent almost certainly insufficient |

---

**Related:** [data-governance.md](data-governance.md) ·
[WORKFLOW.md](../WORKFLOW.md) ·
[PROMPTS.md](../PROMPTS.md) ·
[Evidence pack §F](../learn/06-EVIDENCE-PACK.md#f-singapore-regulatory-context)
