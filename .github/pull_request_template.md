# Pull Request

## What changed

<!-- Brief description of the change -->

## Why

<!-- What triggered this? An incident, a repeated question, a regulatory update,
     a gap someone hit? The "why" is what a reader needs in six months. -->

## Related issue

<!-- Closes #___ -->

---

## Checklist

### Data protection — required

- [ ] **No personal data** — no names, NRIC/FIN, phone numbers, email addresses, dates of
      birth, or addresses
- [ ] **No client-confidential material** — no real pricing, bid strategy or contract terms
- [ ] **No credentials, tokens or internal URLs**
- [ ] I have **read my own diff** before requesting review

> ⚠️ [Git never forgets](../compliance/data-governance.md#git-never-forgets). Deleting a
> file in a later commit does **not** remove it from history, and this repository is
> **public**. Check before you push, not after.

### Content

- [ ] Links tested and working
- [ ] [CHANGELOG.md](../CHANGELOG.md) updated
- [ ] [INDEX.md](../INDEX.md) updated *(if a file was added or removed)*
- [ ] Any statistic cited has a source in
      [the evidence pack](../learn/06-EVIDENCE-PACK.md)

### Governance

- [ ] Does this affect compliance, data protection, or a client deliverable?
      → **If yes, DPO or Compliance review is required before merge**
- [ ] Affected teams identified for notification after merge

---

## Reviewer notes

<!-- Anything the reviewer should look at specifically -->

---

> This PR **is** the change-control record. The review and approval below are the
> `interrupt_before` gate on our own operating procedures — see
> [SOP-05](../WORKFLOW.md#sop-05--changing-an-sop).
