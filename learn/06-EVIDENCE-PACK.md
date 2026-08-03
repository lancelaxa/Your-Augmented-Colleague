# 06 — Evidence Pack

> Teaching repository. All examples use fictional data. See [disclaimer](../README.md#-disclaimer).

**Every statistic in this repository, with its source.** Built for building slides.

---

## ⚠️ How to use these numbers responsibly

Read this before quoting anything below.

1. **These are secondary sources.** Most are industry blogs, vendor research and
   practitioner analyses, not peer-reviewed studies. They are directionally useful and are
   the best available public material on a field that is roughly eighteen months old.
2. **Verify before external use.** Fine for internal education. Before anything goes into
   a client deck, a tender response or a public statement, **follow the link and confirm
   the figure at source.**
3. **Vendor sources have vendor incentives.** Framework and observability vendors publish
   much of this. The reliability mathematics is verifiable arithmetic and does not depend
   on the source; adoption and ROI figures deserve more scepticism.
4. **The field moves fast.** Loop engineering was named in June 2026. Anything here has a
   short shelf life — re-check before reuse.
5. **The compliance section is not legal advice.** Confirm with Legal/DPO before relying
   on it.

---

## A. The reliability mathematics

**The most important data in this repo.** It is arithmetic, so it is independent of any
vendor's interest — `p^N` is `p^N`.

| Finding | Figure | Source |
|---|---|---|
| 95% per-step accuracy over **10 steps** | **59.9%** end-to-end | [Zartis](https://www.zartis.com/the-compounding-errors-problem-why-multi-agent-systems-fail-and-the-architecture-that-fixes-it/) |
| Three agents at 95% each | **86%** end-to-end | [Kore.ai](https://www.kore.ai/blog/multi-agent-systems-fault-line) |
| Three agents at 70% each | **34%** end-to-end | [Kore.ai](https://www.kore.ai/blog/multi-agent-systems-fault-line) |
| Chaining **five** agents | drops to **77%** | [MindStudio](https://www.mindstudio.ai/blog/multi-agent-reliability-compounding-problem-77-percent) |
| 99.9% per step over **100 steps** | only **90.5%** | [Corvair](https://corvair.ai/six-sigma/compound-error.html) |
| 95% per step over **100 steps** | fails **99.4%** of the time | [Corvair](https://corvair.ai/six-sigma/compound-error.html) |
| 1% per-token error rate | **87% cumulative failure by token 200** | [Corvair](https://corvair.ai/six-sigma/compound-error.html) |
| Human checkpoints | **reset accumulated failure risk** to a verified state | [Zartis](https://www.zartis.com/the-compounding-errors-problem-why-multi-agent-systems-fail-and-the-architecture-that-fixes-it/) |

### The full compounding table (computed from `p^N`)

| Per-step | 3 steps | 5 steps | 10 steps | 20 steps | 50 steps | 100 steps |
|---|---|---|---|---|---|---|
| 70% | 34.3% | 16.8% | 2.8% | 0.1% | ~0% | ~0% |
| 80% | 51.2% | 32.8% | 10.7% | 1.2% | ~0% | ~0% |
| 90% | 72.9% | 59.0% | 34.9% | 12.2% | 0.5% | ~0% |
| 95% | 85.7% | 77.4% | 59.9% | 35.8% | 7.7% | 0.6% |
| 99% | 97.0% | 95.1% | 90.4% | 81.8% | 60.5% | 36.6% |
| 99.9% | 99.7% | 99.5% | 99.0% | 98.0% | 95.1% | 90.5% |

**The slide-ready takeaway:** *"A 95%-accurate agent is a 60% -accurate workflow after ten
steps. The fix is not a better model — it is fewer steps, mechanical checks, and human
checkpoints that reset the decay."*

---

## B. Agent failure and reliability in production

| Finding | Figure | Source |
|---|---|---|
| Leading cause of production agent incidents | **>60% are state-management failures** | [Atlan](https://atlan.com/know/ai-agent/ai-agent-memory/what-is-langgraph/) |
| Failed attempts raise per-step error rate | **7.1×** over baseline *(Rutgers, May 2026)* | [via Latitude](https://latitude.so/blog/ai-agent-failure-detection-guide) |
| Agent projects failing in production | **70–95%** | [Fiddler AI](https://www.fiddler.ai/blog/ai-agent-failure-rate) |
| The six agent-specific failure modes | tool misuse · context loss · goal drift · retry loops · cascading errors · silent quality degradation | [Latitude](https://latitude.so/blog/ai-agent-failure-detection-guide) |
| Context rot | performance degrades progressively as the window fills | [Latitude](https://latitude.so/blog/ai-agent-failure-detection-guide) |

**Slide-ready:** *"The constraint on agentic AI is not intelligence. It's state,
verification and error compounding — architecture problems, not model problems."*

---

## C. Adoption and productivity

Present sections C1 and C2 **together**. Either alone is misleading.

### C1 — Individual gains are real

| Finding | Figure | Source |
|---|---|---|
| Knowledge workers using AI at work | **75%** | [Makerstations](https://www.makerstations.io/ai-adoption-at-work-statistics/) |
| Say AI lets them spend more time on high-value work | **66%** *(Microsoft Work Trend Index 2026, n=20,000)* | [Makerstations](https://www.makerstations.io/ai-adoption-at-work-statistics/) |
| Producing work they couldn't have a year ago | **58%** | [Makerstations](https://www.makerstations.io/ai-adoption-at-work-statistics/) |
| Average work hours saved | **5.4%** (~2.2 hrs per 40-hr week) | [Saner.ai](https://blog.saner.ai/ai-productivity-statistics/) |
| Daily users saving 4+ hours/week | **33.5%** | [Saner.ai](https://blog.saner.ai/ai-productivity-statistics/) |

### C2 — Organisational gains mostly are not

| Finding | Figure | Source |
|---|---|---|
| Firms seeing **zero measurable** productivity impact | **89%** *(study of 6,000 executives)* | [Saner.ai](https://blog.saner.ai/ai-productivity-statistics/) |

**Slide-ready — the central argument of this repo:**

> *"66% of individuals say AI helps. 89% of firms measure no impact. The gap is not the
> model — everyone has the same models. The gap is that individual improvements are never
> written down, versioned, reviewed or re-run. That is a systems problem, and it is the
> one we are solving."*

### C3 — Recruitment and HR specifically

| Finding | Figure | Source |
|---|---|---|
| Increase in candidate quality where AI used in recruitment | **20%** | [Careertrainer](https://careertrainer.ai/en/reports/ai-in-hr-statistics/) |
| HR teams experimenting with generative AI | **40%** | [Careertrainer](https://careertrainer.ai/en/reports/ai-in-hr-statistics/) |

---

## D. The terminology, dated

Useful for establishing that this is a genuinely current field.

| Term | Origin | Key sources |
|---|---|---|
| **Prompt engineering** | ~2020–2022 | Widely established |
| **Context engineering** | ~2025 | [LangChain](https://www.langchain.com/blog/context-engineering-for-agents) · four pillars: write, select, compress, isolate |
| **Loop engineering** | **Coined June 2026** | [Addy Osmani](https://addyosmani.com/blog/loop-engineering/) · [O'Reilly Radar](https://www.oreilly.com/radar/loop-engineering/) · Peter Steinberger's one-liner |
| **Harness engineering** | 2026 | Connecting the model to an executable environment |
| **Graph engineering** | 2024–2026 | [LangGraph, 3 years of graph engineering](https://www.langchain.com/blog/3-years-of-graph-engineering-with-langgraph) |

### Quotable definitions

> **Prompt engineering** asks: *"What should I say to get the best output?"*
> **Loop engineering** asks: *"What system should I build so the agent finds the work, does
> it, verifies it, and remembers what it did — without me in the loop at all?"*

> Loop engineering swaps you out as *"the person who hits enter"* and turns you into *"the
> person who designs the loop."*

> Prompt-by-prompt supervision **stopped scaling with review capacity.**
> — Addy Osmani, on why the shift happened

> Agents tend to aim for **"looks done"** unless a verifier and stop rules gate every
> iteration.

> The whole reason you split the verifier sub-agent from the maker is to make the loop's
> "it's done" mean something — and even then, **"done" is a claim and not a proof.**

> **Loops = one agent's behaviour. Graphs = the org structure connecting many agents.**

> The skill is **curation, not accumulation.** *(on context engineering)*

> Context engineering is the art and science of filling the context window with **just the
> right information at each step** of an agent's trajectory. — LangChain

---

## E. Architecture findings

| Finding | Detail | Source |
|---|---|---|
| Patterns that earn their cost in production | **Hierarchical (supervisor-worker) and graph.** Swarm and blackboard "rarely outperform" them | [Digital Applied](https://www.digitalapplied.com/blog/agent-architecture-patterns-taxonomy-2026) |
| The five workflow patterns | prompt chaining · routing · parallelisation · orchestrator-workers · evaluator-optimizer | [Redis](https://redis.io/blog/ai-agent-architecture-patterns/) |
| Graph primitives | **State, Nodes, Edges** — what it knows, what it can do, how it decides | [Atlan](https://atlan.com/know/ai-agent/ai-agent-memory/what-is-langgraph/) |
| Checkpointing | Full state persisted after every node; navigable **like Git commits** — inspect, rewind, fork | [Atlan](https://atlan.com/know/ai-agent/ai-agent-memory/what-is-langgraph/) |
| Human-in-the-loop pitfall | `interrupt_after` means **the action already happened** before the pause | [AI Practitioner](https://aipractitioner.substack.com/p/human-in-the-loop-agents-steering) |
| Orchestrator-workers division | Orchestrator holds global state and error recovery; **workers are stateless** | [Augment Code](https://www.augmentcode.com/guides/multi-agent-orchestration-architecture-guide) |
| Loop anatomy (Osmani) | automations · worktrees · skills · connectors · sub-agents · **external state** | [Addy Osmani](https://addyosmani.com/blog/loop-engineering/) |

---

## F. Singapore regulatory context

> ⚠️ **Not legal advice.** Dates and thresholds must be confirmed with Legal/DPO and at
> source before any operational or client-facing reliance. Included to show the shape of
> the obligations, not to substitute for advice.

| Finding | Detail | Source |
|---|---|---|
| PDPC Advisory Guidelines on Use of Personal Data in Generative AI | Issued **20 July 2026**; covers development, deployment, post-deployment | [PDPC](https://www.pdpc.gov.sg/organisations/regulations-decisions/public-consultations/public-consultation-on-the-proposed-advisory-guidelines-on-use-of-personal-data-in-generative-ai) · [Allen & Gledhill](https://www.allenandgledhill.com/sg/publication/articles/33126/pdpc-consults-on-proposed-advisory-guidelines-on-use-of-personal-data-in-generative-ai) |
| AI-Specific Notifications | Generic notices (e.g. "new product development") are **insufficient** for consent to AI training | [Baker McKenzie](https://www.bakermckenzie.com/en/insight/publications/2026/07/singapore-ai-specific-notification-requirement) |
| NRIC general rule | Organisations **generally prohibited** from collecting/using/disclosing NRIC unless required by law or necessary to verify identity to a high degree of certainty | [Bird & Bird](https://www.twobirds.com/en/insights/2018/singapore/pdpc-issues-new-advisory-guidelines-in-singapore) |
| NRIC as credential | Must **not** be used as password, login ID or default credential | PDPC–CSA Joint Advisory (June 2025) |
| NRIC authentication deadline | Stop using NRIC for authentication by **31 Dec 2026** | [Baker McKenzie](https://www.bakermckenzie.com/en/insight/publications/2026/02/singapore-pdpc-to-ban-nric-authentication-use-by-end-2026) |
| PDPA financial penalties | Up to **S$1 million**, or **10% of annual turnover** in Singapore for organisations with turnover exceeding S$10m | [Lexology](https://www.lexology.com/library/detail.aspx?g=292372a8-b62c-4a2e-84ab-24ea4b3f2b66) |
| IMDA Model AI Governance Framework for Generative AI | Covers hallucination, bias, IP, content provenance, cybersecurity, systemic risk | [PDPC](https://www.pdpc.gov.sg/help-and-resources/2020/01/model-ai-governance-framework) |
| AI Verify | Technical testing **+ process checks**: transparency, explainability, fairness, safety, accountability | [AI Governance Institute](https://aigovernance.com/entry/ai-verify-testing-framework-singapore-imda) |
| Procurement direction | AI Verify and ISAGO being embedded into **public-sector procurement standards** | [Pertama Partners](https://www.pertamapartners.com/insights/ai-regulations-singapore-imda-compliance) |
| Status | Frameworks **voluntary** but widely referenced across ASEAN | [Pertama Partners](https://www.pertamapartners.com/insights/singapore-model-ai-governance-framework-genai-agentic) |

**Slide-ready:** *"Singapore's approach is framework-driven and largely voluntary — but
AI Verify is moving into public-sector procurement standards. For a firm bidding on
government work, demonstrable AI governance is becoming a commercial qualification, not
just a compliance overhead."*

---

## G. Company context

| Finding | Detail | Source |
|---|---|---|
| CGP Group founded | 2012 | [CGP Group](https://www.cgpgroup.com/about) |
| Scale | 20 offices, 700+ team members, network across 40 countries | [CGP Group](https://www.cgpgroup.com/about) |
| Singapore service lines | Executive Search, Contracting, **RPO**, HR Outsourcing | [CGP Singapore](https://www.cgp.sg/about-us/) |
| Sector coverage includes | **Government & Public Sector**, Financial Services, Life Sciences, Industrial & Aerospace, HR, Healthcare | [Clutch profile](https://clutch.co/profile/cornerstone-global-partners-cgp-singapore-executive-recruitment-firm) |

> ℹ️ Compiled from public secondary sources — `cgp.sg` was not directly reachable from the
> build environment. **Verify against your own internal materials** before external use.

---

## Suggested slide order

For a 30-minute leadership session:

1. **The gap** — C1 + C2 together (66% vs 89%). *Why the tool isn't the answer.*
2. **The four rungs** — the ladder diagram from [00](00-START-HERE.md).
3. **The new vocabulary** — D, with the Osmani quotes. *This was named in June 2026.*
4. **The hard constraint** — the compounding table from A. *95% → 59.9%.*
5. **Therefore: verifiers and human gates** — B + the checkpoint-reset finding.
6. **What good looks like** — the Monday tender loop from [03](03-LOOP-ENGINEERING.md#8-worked-example-the-monday-morning-tender-loop).
7. **The governance angle** — F. *AI Verify is entering procurement standards.*
8. **The ask** — the maturity ladder from [03](03-LOOP-ENGINEERING.md#9-the-loop-maturity-ladder). *We are at level 0. Levels 1–2 are free.*

---

Next → [07 — GitHub for Non-Coders](07-GITHUB-FOR-NON-CODERS.md)
