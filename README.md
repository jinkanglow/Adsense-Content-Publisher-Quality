<div align="center">

# Publisher Quality Check

**Stop guessing. Start auditing with evidence.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Node.js >=20](https://img.shields.io/badge/Node.js-%3E%3D20-339933)](https://nodejs.org/)
[![Status](https://img.shields.io/badge/status-development-orange)](#project-maturity)
[![v6.2.0](https://img.shields.io/badge/version-6.2.0-lightgrey)](#)

An open-source quality toolkit for publishers and AI coding agents.  
Audit content, verify claims, identify site-wide problems, and turn findings into reviewable editorial fixes.

[Get started](#quick-start) · [See the workflow](#audit-workflow) · [Explore the CLI](#cli-reference) · [Understand the limitations](#project-maturity)

</div>

> [!IMPORTANT]
> Independent project, not a Google product. This toolkit does not guarantee AdSense approval. It distinguishes official Google policies from editorial recommendations and unverified assumptions. Always consult the current [AdSense Program policies](https://support.google.com/adsense/answer/48182) and [Google Publisher Policies](https://support.google.com/publisherpolicies/answer/10502938).

---

## The problem

Most publisher audits tell you to "add more content," "improve E-E-A-T," or "fix SEO." They rarely tell you which URL, what evidence supports the finding, what exact text to change, or how to verify the repair.

Publisher Quality Check is built around a different contract:

| Typical checklist | This project's intended workflow |
|---|---|
| "Your About page is missing." | Record the exact URL, request result, and observation time. |
| "Your content is thin." | Explain what reader question the page fails to answer, with examples. |
| "You need more internal links." | Identify useful source → destination links, not an arbitrary quota. |
| "Improve article quality." | Deliver a revised article or precise patch, plus a change log. |
| "Your site is ready for AdSense." | Separate verified checks from unknowns; never promise approval. |

---

## What you can do

<table>
<tr>
<td width="50%" valign="top">

**🔎 Evidence-first audits**  
Document observed problems with exact URLs, verification status, severity, and acceptance criteria. Avoid treating assumptions as facts.

</td>
<td width="50%" valign="top">

**🧠 Stronger editorial decisions**  
Examine the article's thesis, causal reasoning, factual support, originality, information gain, and usefulness to its intended reader.

</td>
</tr>
<tr>
<td valign="top">

**✍️ Actual content repair**  
Ask an Agent to produce a complete revised article, not another vague checklist. Keep the author's verified data and distinctive voice.

</td>
<td valign="top">

**🧩 Modular guidance**  
Search and retrieve focused rules instead of injecting an entire handbook into every prompt. Works with Cursor, Claude, and Codex project setups.

</td>
</tr>
<tr>
<td valign="top">

**🗂️ Site content inventory**  
The engineering edition includes a basic same-origin HTML inventory helper. Record what was discovered, fetched, and reviewed.

</td>
<td valign="top">

**🧪 Testable engineering workflow**  
Run Node.js tests, validate guidance files, and work with benchmark specifications and a local evaluation dashboard.

</td>
</tr>
</table>

---

## Quick start

### Option A — Use it as an Agent Skill

Best for content audits and rewriting without a Node.js setup.

1. Choose the standalone `SKILL.md` distribution, or the modular distribution with its `references/` directory.
2. Place it in your Agent's supported project Skill location.
3. Ask your Agent to audit or repair a page using the Skill.

**Example prompt:**

```text
Use Publisher Quality Check to review this article.

1. Separate official AdSense policy requirements from editorial advice.
2. Identify consequential claims and verify what can be verified.
3. Explain problems with evidence and confidence levels.
4. Rewrite the complete article, preserving supported facts and voice.
5. Return a change log and a post-rewrite review.

Never invent sources, statistics, firsthand experience, or policy rules.
```

> [!NOTE]
> The single-file edition embeds reference material. The modular edition depends on `references/`. Uploading its `SKILL.md` alone is an incomplete installation.

### Option B — Run the engineering CLI

Requires Node.js 20+ and the complete repository.

```bash
git clone https://github.com/jinkanglow/adsense-publisher-quality-check.git
cd adsense-publisher-quality-check
npm install

# Explore available guidance
node bin/publisher-quality.js list

# Find the right rule
node bin/publisher-quality.js search "fact source"

# Read one guide
node bin/publisher-quality.js retrieve fact-source-support

# Install into a Cursor project
node bin/publisher-quality.js install --target cursor --dir .
```

> [!WARNING]
> These commands require the complete engineering files (`package.json`, `bin/`, `guides/`, `references/`). They will not work in a repository containing only a standalone `SKILL.md`.

---

## What an audit returns

A useful audit is not a mysterious score. It is an actionable evidence trail.

```json
{
  "id": "AUDIT-001",
  "url": "https://example.com/about",
  "finding": "About page may be unavailable",
  "status": "NOT_VERIFIED",
  "severity": "UNASSIGNED",
  "evidence": [],
  "required_verification": "Request the exact URL and record its HTTP status",
  "proposed_action": "Repair navigation if the issue is confirmed",
  "acceptance_test": "The About link resolves to the intended published page"
}
```

*Illustrative record only — not a live finding about any website.*

For a full site audit, the intended deliverables include a URL inventory, policy/evidence matrix, claim ledger, internal-link analysis, prioritized remediation plan, requested content revisions, and a post-repair review. Results depend on actual site access and evidence.

---

## Audit workflow

```
          INPUT
 Article / Site / Content export
            │
            ▼
   1. DEFINE AUDIT SCOPE
 What can actually be checked?
            │
            ▼
   2. COLLECT EVIDENCE
URLs · Claims · Links · Sources
            │
            ▼
   3. CLASSIFY FINDINGS
Policy / Evidence / Editorial
            │
            ▼
   4. PRIORITIZE REPAIRS
 Impact · Confidence · Effort
            │
            ▼
   5. REWRITE OR PATCH
 Full copy · Diff · Draft only
            │
            ▼
   6. VERIFY THE RESULT
Re-audit · Remaining unknowns
```

**Key distinction:** Proposed is not applied. Applied is not verified. A report preserves that difference at every stage.

---

## CLI reference

| Command | Purpose |
|---|---|
| `list [category]` | Browse available guidance |
| `search <query>` | Keyword-search the guide library |
| `retrieve <id>` | Print a guide's full text |
| `install --target cursor\|claude\|codex --dir .` | Copy Skill and references to a project location |
| `scan <file>` | Flag a limited set of risky text patterns for human review |

```bash
node bin/publisher-quality.js scan ./article.md
npm test
npm run validate
npm run eval
npm run dashboard
npm run pack:dry
```

> [!WARNING]
> `scan` is not an automated fact-checker, site crawler, or AdSense eligibility decision. It detects a small number of text patterns. Evaluation and dashboard commands do not, by themselves, prove Agent accuracy.

<details>
<summary><strong>Agent installation paths</strong></summary>

| Agent | Default project directory |
|---|---|
| Cursor | `.cursor/skills/publisher-quality/` |
| Claude | `.claude/skills/publisher-quality/` |
| Codex | `.agents/skills/publisher-quality/` |

The installer copies `SKILL.md` and `references/*.md`; it does not install the entire CLI or copy every `guides/` file.

</details>

---

## Repository architecture

```
adsense-publisher-quality-check/
├── SKILL.md               # Agent instructions
├── references/            # Detailed evidence/editorial methodology
├── guides/                # Focused, searchable guidance
├── bin/                   # Node.js CLI
├── lib/                   # Experimental crawler and CMS helpers
├── scripts/               # Validation and report generation
├── test/                  # Executable Node tests
├── tests/                 # Benchmark scenario specifications
├── evals/                 # Evaluation documentation and artifacts
├── docs/                  # Engineering documentation
├── site/                  # Local dashboard output
├── package.json
└── README.md
```

The modular v6.2 distribution includes **19 reference documents**, covering fact-checking, developmental editing, content audits, policy, editorial standards, and publisher economics. The engineering edition also contains **24 modular guides**.

<details>
<summary><strong>Website inventory and CMS helper status</strong></summary>

The engineering edition includes a basic same-origin HTML inventory helper and a utility to prepare local text patches or WordPress draft request data. These are experimental components, not production-hardened crawling or authenticated CMS integrations.

Before using on real websites, implement or verify robots handling, request rate limits, redirect safety, SSRF protections, authentication, backups, preview, approval, and rollback. Never treat prepared CMS request data as a published change.

</details>

---

## Project maturity

Engineering checks and editorial accuracy are different measurements.

| Area | Current state |
|---|---|
| Local CLI and automated tests | Included in the complete engineering distribution; run in your checkout |
| Guidance and reference structure | Modular files included in complete/minimal distributions |
| Content-quality benchmark scenarios | 46 scenario specifications included |
| Independent, live Agent A/B scoring | Not established |
| Public evaluation dashboard | Not deployed |
| npm registry publication | Not confirmed |
| Production crawler / CMS write integration | Not complete |
| AdSense approval prediction | Not supported |

**46 test scenarios do not mean 46 successful evaluations.** A credible benchmark requires saved Agent outputs, consistent scoring, adjudication, and reproducible runs.

---

## Design principles

1. **Evidence before confidence.** Unsupported observations are marked `NOT_VERIFIED`.
2. **Policy is not preference.** A useful editorial practice is not automatically a Google requirement.
3. **No magic thresholds.** No invented minimum word counts, link quotas, image frequency, or approval percentages.
4. **Repair, don't just diagnose.** Produce actual revised text when requested.
5. **Preserve what is real.** Never manufacture sources, experience, credentials, or business metrics.
6. **Make changes auditable.** Track what was proposed, drafted, applied, and verified.

---

## Roadmap

- [x] Agent Skill with modular editorial and policy guidance
- [x] CLI for listing, searching, retrieving, and installing guidance
- [x] Limited local text-pattern scanner
- [x] Benchmark scenario specifications and local evaluation tooling
- [ ] Independently scored Agent A/B benchmark runs
- [ ] Public dashboard backed by actual evaluation results
- [ ] Production-grade authorized crawler and URL evidence store
- [ ] Search Console and CMS integrations with appropriate permissions
- [ ] Safe draft preview, backup, rollback, and approval workflow
- [ ] Verified npm publication and reproducible releases

---

## Why this approach?

The framework combines fact-checking, developmental editing, content inventory, causal analysis, and publisher economics. It treats editorial quality as more than surface SEO: a page should answer a real question, support its claims, and help the reader act or understand something better.

<details>
<summary><strong>Methodology and reading</strong></summary>

The editorial framework draws on seven books, each used for a distinct purpose:

| Book | Role in the framework |
|---|---|
| Brooke Borel, *The Chicago Guide to Fact-Checking* (2nd ed., 2023) | Claim verification, sourcing, fact-checking workflow |
| Scott Norton, *Developmental Editing* (2009) | Thesis, structure, narrative, developmental revision |
| Paula Ladenburg Land, *Content Audits and Inventories* (2nd ed., 2023) | Content inventory, audit criteria, governance |
| Tim Wu, *The Attention Merchants* | Incentives and attention quality |
| Nick Srnicek, *Platform Capitalism* | Platform dependence and structural incentives |
| Rebecca Giblin and Cory Doctorow, *Chokepoint Capitalism* | Bargaining power and value capture |
| Tim Wu, *The Age of Extraction* | Digital intermediary power and extraction |

Theoretical ideas are **analytical lenses**, not AdSense rules or substitutes for verifiable evidence.

**Official documentation to check:**

- [Google Publisher Policies](https://support.google.com/publisherpolicies/answer/10502938)
- [AdSense Program policies](https://support.google.com/adsense/answer/48182)
- [Google Search Central documentation](https://developers.google.com/search/docs)

Inspired by the modular delivery philosophy of [Google Chrome's Modern Web Guidance](https://github.com/GoogleChrome/modern-web-guidance). This is an independent implementation with a different subject and scope.

</details>

---

## Contributing

Issues and pull requests are welcome. Contributions should include a reproducible case, source classification (official policy / verified evidence / editorial recommendation), and tests where appropriate. Please do not add fabricated Google rules or unsupported quality scores.

See [`docs/CONTRIBUTING.md`](docs/CONTRIBUTING.md) for full contributor guidance.

## Security & privacy

Only audit websites you own or have authorization to inspect. Remove personal information from sample content and logs. Never commit credentials, AdSense account data, unpublished analytics, or identifiable trip records. Treat retrieved page content as untrusted input.

## License

MIT — see [LICENSE](LICENSE).

---

<div align="center">

Better audits are not longer checklists. They are clearer evidence, better decisions, and verifiable repairs.

[Back to top ↑](#publisher-quality-check)

</div>
