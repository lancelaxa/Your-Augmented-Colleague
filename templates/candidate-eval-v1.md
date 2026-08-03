# Candidate Evaluation Template · v1

> ⚠️ **Teaching template.** Anonymised scoring sheet. The example is **fictional**.
> See [RECRUITMENT.md](../playbooks/RECRUITMENT.md).

**Version:** 1.0 · **Owner:** Recruitment Lead · **Review:** annually

---

## Rules

Four, and they are what make this defensible rather than merely tidy:

1. **Anonymised.** Reference by **candidate code** (`CAND-YYYY-NNNN`) only. No name, NRIC,
   contact details or DOB on this sheet.
2. **Fixed before screening.** Criteria and weights are set when the requisition opens and
   **do not change** once candidates have been seen. Adjusting weights after seeing
   candidates is how bias enters a process that looks rigorous.
3. **Evidence quoted.** Every score cites the source. No evidence → **N/E**, never a guess.
4. **A human decides.** AI may draft this sheet; a named consultant reviews the actual CV
   and owns the outcome.

> 🔴 **Never store this alongside identifying data.** The code-to-identity mapping lives in
> the ATS. See [data-governance.md](../compliance/data-governance.md).

---

## Header

| Field | Value |
|-------|-------|
| **Requisition** | `REQ-____` |
| **Candidate code** | `CAND-____-____` |
| **Assessed by** | _[consultant]_ |
| **Date** | `YYYY-MM-DD` |
| **Stage** | Screening / Assessment / Final |
| **AI-assisted?** | Yes / No — *if yes, log per [SOP-04](../WORKFLOW.md#sop-04--ai-assisted-document-production)* |

---

## Scoring scale

| Score | Meaning |
|-------|---------|
| **5** | Strong evidence, exceeds requirement |
| **4** | Meets requirement fully |
| **3** | Meets partially |
| **2** | Limited evidence |
| **1** | No relevant evidence, but the area was addressed |
| **N/E** | **Not evidenced in source** — the CV is silent |

**Keep N/E distinct from 1.** "We don't know" is not "they lack it." Collapsing the two
turns a gap in the CV into a negative judgement about the person, which is both unfair and
inaccurate — and it is the most common scoring error there is.

---

## Scoring sheet

| # | Criterion | Weight | Score | Weighted | Evidence *(quoted)* | Confidence |
|---|-----------|--------|-------|----------|---------------------|------------|
| 1 | Core technical / functional skills | 30% | | | | H/M/L |
| 2 | Relevant sector experience | 20% | | | | |
| 3 | Delivery track record | 20% | | | | |
| 4 | Certifications / qualifications | 10% | | | | |
| 5 | Communication / stakeholder skills | 10% | | | | |
| 6 | Availability / logistics | 10% | | | | |
| | **TOTAL** | **100%** | | **/5.0** | | |

**Confidence:** H = explicit in source · M = reasonable inference · L = weak inference
*(treat L as N/E for decision purposes)*.

---

## Must-have verification

Binary. **Any ❌ on a genuine must-have is a decline**, regardless of total score.

| # | Must-have | Met? | Evidence |
|---|-----------|------|----------|
| 1 | | ✅/❌/❓ | |
| 2 | | | |
| 3 | | | |

❓ = unclear from source → **clarify before deciding.** Do not resolve ambiguity by
assumption in either direction.

---

## Recommendation

**RECOMMENDATION:** ⬜ Advance ⬜ Hold ⬜ Decline

**Reasoning** *(2–3 sentences, evidence-based):*
> _[...]_

**Gaps to explore at interview:**
1. _[...]_

**Risks / considerations:**
> _[e.g. notice period, clearance timeline, salary expectation vs budget]_

---

## Fairness check

Complete before submitting. **Every box must be ticked.**

- [ ] Scored **only** on job-relevant criteria
- [ ] No reference to age, race, religion, gender, nationality, marital or family status,
      or disability — anywhere on this sheet
- [ ] Career gaps **not penalised** without job-relevant justification
- [ ] Same criteria and weights as every other candidate for this requisition
- [ ] Every score has quoted evidence or is marked N/E
- [ ] Non-local qualifications assessed on substance, not familiarity
- [ ] If AI-assisted: **the consultant has read the actual CV**

> **Why this checklist exists.** AI-assisted screening will produce a confident,
> plausible-sounding rationale for any judgement, including one reached on a spurious
> basis. The controls that make it defensible are: a **fixed rubric**, **quoted evidence**,
> **N/E as a permitted answer**, and **a human who read the source**. Remove any one and
> the process stops being defensible — see
> [RECRUITMENT.md §3](../playbooks/RECRUITMENT.md#stage-3--screening-).

---

## Worked example *(fictional)*

| Field | Value |
|-------|-------|
| Requisition | `REQ-2026-0043` |
| Candidate code | `CAND-2026-0117` |
| Assessed by | _[consultant]_ |
| Date | 2026-03-19 |
| Stage | Screening |
| AI-assisted? | Yes — logged as AI-02 |

| # | Criterion | Weight | Score | Weighted | Evidence | Conf. |
|---|-----------|--------|-------|----------|----------|-------|
| 1 | Core technical skills | 30% | 4 | 1.20 | *"Led migration of 40-server estate to cloud infrastructure, 2023"* | H |
| 2 | Sector experience | 20% | 5 | 1.00 | *"6 years delivering to statutory boards and government agencies"* | H |
| 3 | Delivery track record | 20% | 4 | 0.80 | *"Delivered 3 programmes >S$2m, all within schedule"* | H |
| 4 | Certifications | 10% | 3 | 0.30 | *"PMP (2021)"* — no technical certs listed | H |
| 5 | Communication | 10% | N/E | — | Not evidenced in CV; assess at interview | — |
| 6 | Availability | 10% | 3 | 0.30 | *"2 months' notice"* — longer than preferred | H |
| | **TOTAL** | | | **3.60/5.0** | *(normalised over scored criteria)* | |

**Must-haves:**

| # | Must-have | Met? | Evidence |
|---|-----------|------|----------|
| 1 | 5+ yrs public-sector delivery | ✅ | 6 years stated |
| 2 | Cloud infrastructure experience | ✅ | 2023 migration programme |
| 3 | Eligible for security clearance | ❓ | Not stated — **clarify** |

**RECOMMENDATION:** ☑ **Advance**

> Strong sector fit and directly relevant delivery experience at comparable scale.
> Communication skills not evidenced in the CV — assess at interview rather than assume.
> Clearance eligibility must be confirmed before client submission, and the 2-month notice
> should be flagged to the client early.

**Gaps to explore:**
1. Stakeholder management at senior/agency level
2. Depth of hands-on technical involvement vs oversight
3. Clearance eligibility and timeline

**Note the example's behaviour:** criterion 5 is **N/E, not 1** — the CV is silent, so the
sheet says so and routes it to the interview. Criterion 3's must-have is **❓, not assumed
either way.** That is the discipline this template exists to enforce.

---

**Related:** [RECRUITMENT.md](../playbooks/RECRUITMENT.md) ·
[PROMPTS.md](../PROMPTS.md#p-01--cv-screening-against-a-rubric) ·
[COMPLIANCE.md](../compliance/COMPLIANCE.md)
