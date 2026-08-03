# audit-logs.md — Audit Trail (Demonstration)

> ## 🚨 FICTIONAL DEMONSTRATION DATA
> Every entry below is invented for teaching purposes. No real project, personnel, decision
> or incident is recorded here. Real audit logs belong in a **private** repository or a
> controlled system of record. See [data-governance.md](../compliance/data-governance.md).

---

## Why an audit log

Three reasons, in ascending order of how often they actually bite:

1. **Regulatory.** IMDA's governance frameworks and the AI Verify approach emphasise
   accountability, transparency and **process checks** — not just outputs. An audit trail is
   the evidence that governance happened.
2. **Contractual.** Public-sector engagements require demonstrable change control and
   sign-off history.
3. **Practical.** Six months on, nobody remembers why the deadline moved or who approved
   the scope change. This is the reason you will actually use it.

> **The good news:** most of this is a **by-product** of working properly rather than extra
> work. PR approvals, issue history and commit messages generate the trail automatically —
> see [checkpointing](../learn/04-GRAPH-ENGINEERING.md#4-checkpointing-time-travel-and-recovery).
> What is logged here is only what those artefacts do not capture.

---

## What to log — and what not to

### ✅ Log

| Event | Why |
|-------|-----|
| Milestone submission and acceptance | Contractual |
| Scope or timeline change | Contractual + commercial |
| Approval exercised under the authority matrix | Governance |
| **AI materially contributing to a decision or deliverable** | AI governance |
| Data incident or near-miss | Regulatory |
| Vendor approval | Procurement |
| SOP change affecting a client deliverable | Change control |
| Access granted to CONFIDENTIAL/RESTRICTED | Security |

### 🚫 Do not log

- **Personal data of any kind.** Reference by role or ID, never by name-plus-identifier.
- Routine AI use for drafting. *(Logging everything produces a log nobody reads — which is
  worse than no log, because it looks like control.)*
- Anything already captured in the PR/issue history. Reference it instead of duplicating it.

---

## Log format

```
| Date | Ref | Event | Actor | Detail | Approved by | Link |
```

**Conventions:** ISO dates (`YYYY-MM-DD`) · roles or IDs, never names-plus-identifiers ·
link to the issue/PR rather than restating it · **append only, never edit.** A correction
is a new row referencing the old one — an edited audit log is not an audit log.

---

## Project log — PROJ-DEMO-01 *(fictional)*

| Date | Ref | Event | Actor | Detail | Approved by | Link |
|------|-----|-------|-------|--------|-------------|------|
| 2026-01-15 | M1 | Milestone submitted | Delivery Mgr | Mobilisation pack, 5 criteria evidenced | Partner | #12 |
| 2026-01-18 | M1 | Milestone accepted | Client sponsor | No conditions | — | #12 |
| 2026-02-03 | — | Vendor approved | HQ Ops | Training vendor, < S$50k, DPA executed | HQ Ops Lead | #18 |
| 2026-02-20 | M2 | Milestone submitted | Delivery Mgr | Baseline report v1.2 | Partner | #24 |
| 2026-02-24 | M2 | Acceptance — conditional | Client sponsor | §4 expansion requested | — | #24 |
| 2026-02-28 | M2 | Condition closed | Delivery Mgr | v1.3 submitted, accepted | Partner | #24 |
| 2026-03-05 | CR-01 | **Scope change** | Client sponsor | +1 domain to M3 framework; +2 weeks | Partner + Finance | #31 |
| 2026-03-14 | AI-01 | **AI-assisted deliverable** | Delivery Mgr | Baseline report §3 drafted with AI from workshop notes; fully reviewed and edited by author; no personal data in prompt | Compliance Reviewer | #33 |
| 2026-03-22 | INC-01 | **Near-miss — PII** | Consultant | Unredacted CV pasted into approved enterprise tool. Detected by user, conversation deleted, reported same day. No external exposure. Refresher training delivered to team. | DPO | #35 |
| 2026-04-02 | — | SOP change | HQ Ops | SOP-04 updated: mandatory redaction verification step added following INC-01 | HQ Ops Lead + DPO | PR #38 |
| 2026-04-10 | M3 | Milestone at risk | Delivery Mgr | Client validation workshop slipped 2 weeks; mitigation agreed | — | #40 |

---

## AI usage log *(fictional)*

Logged where AI **materially contributed** to a decision or a client deliverable.

| Date | Ref | Purpose | Tool tier | Data tier | Human reviewer | Output used in |
|------|-----|---------|-----------|-----------|----------------|----------------|
| 2026-03-14 | AI-01 | Draft report §3 from workshop notes | Enterprise | 🔵 INTERNAL | Delivery Mgr | M2 deliverable |
| 2026-03-19 | AI-02 | Screening summaries, 12 candidates | Enterprise | 🔵 INTERNAL *(redacted from 🔴)* | Consultant | Shortlist, REQ-0043 |
| 2026-03-28 | AI-03 | RFP requirements matrix from 84-page tender | Enterprise | 🟢 PUBLIC | Bid Mgr | BD-2026-011 |
| 2026-04-08 | AI-04 | Pricing table arithmetic verification | Enterprise | 🟠 CONFIDENTIAL | Finance | BD-2026-011 |

**Note AI-02:** the data tier is 🔵 **because redaction happened first**. The source was
🔴 RESTRICTED. Recording that transition is exactly what makes the entry defensible — it
demonstrates the control operated, rather than merely asserting that it exists.

---

## Incident log *(fictional)*

| Date | Ref | Severity | Summary | Root cause | Action | Closed |
|------|-----|----------|---------|------------|--------|--------|
| 2026-03-22 | INC-01 | Medium | Unredacted CV entered into approved AI tool | Redaction step not verified before prompting | Mandatory verification added to SOP-04; team refresher | 2026-04-02 |

### The INC-01 pattern — worth studying

This fictional incident shows the response working correctly, and each element is
deliberate:

1. **Self-detected and self-reported.** The person who made the mistake reported it. That
   only happens where reporting is genuinely safe — which is why
   [COMPLIANCE.md](../compliance/COMPLIANCE.md#4-the-nric-rule--read-this-twice) states
   plainly that reporting is never itself a disciplinary matter.
2. **Contained fast.** Conversation deleted, tool was at least an approved enterprise one,
   scope of exposure established.
3. **Root cause identified honestly.** Not "human error" — *the procedure had no
   verification step*. "Human error" is where root-cause analysis goes to die; it names the
   person instead of the system, and it produces no fix.
4. **The system changed.** SOP-04 gained a mandatory verification gate.
5. **The change is traceable** — PR #38, reviewed and approved.

> **A near-miss reported and fixed is worth more than a quarter with no incidents
> recorded.** The second usually means people are not reporting, and the incidents are
> happening anyway — just invisibly.

---

## Quarterly review

- [ ] All required events logged?
- [ ] Any gaps between the log and the PR/issue history?
- [ ] Incidents reviewed for patterns, not just individually?
- [ ] Did SOP changes actually follow from incidents?
- [ ] AI usage log complete for material contributions?
- [ ] Any personal data accidentally recorded here? *(→ escalate immediately)*
- [ ] Retention applied per schedule

---

**Related:** [IMDA-DELIVERABLES.md](IMDA-DELIVERABLES.md) · [WORKFLOW.md](../WORKFLOW.md) ·
[data-governance.md](../compliance/data-governance.md)
