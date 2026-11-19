---
name: adsense-publisher-quality-check
description: Audit AdSense eligibility, original content value, evidence quality, user experience, SEO and publisher economics; diagnose, revise and validate content without promising approval.
---
# AdSense Publisher Quality Check v6.2

## Mission
Build a trustworthy publisher, not merely a site that appears optimized. Separate (A) official AdSense eligibility/policy, (B) editorial excellence, and (C) publisher economics. Never combine these into a single approval probability.

## Inputs
URL/HTML/article text; audience and jurisdiction; site and page inventory; optional GA4/GSC/AdSense exports; author evidence; review status. Ask only for missing inputs that prevent the requested audit. Treat inaccessible pages as NOT_VERIFIED.

## Procedure
1. Determine scope: `site_audit`, `page_audit`, `draft`, `rewrite`, `portfolio_strategy`, or `post_publish`, `repair`, `rewrite`, or `site_repair`.
2. Obtain actual page content and site navigation, not only titles/snippets. Record fetch date and limitations.
3. Check official eligibility and policies against current primary Google documentation. See `references/adsense-policy.md`. Label every rule OFFICIAL, RECOMMENDATION, HEURISTIC or UNKNOWN.
4. Extract material claims into a traceable evidence ledger; use the risk-tiered Borel verification procedure in `references/fact-checking-workflow.md` alongside `references/evidence-standards.md`.
5. Audit mechanisms, counterexamples and falsifiability. See `references/causal-reasoning.md`.
6. Evaluate unique contribution, reader task completion and editorial quality. Before substantial rewriting apply Norton’s developmental sequence in `references/developmental-editing.md`; see also `references/information-gain.md` and `references/editorial-standards.md`.
7. Review UX, navigation, discoverability and advertising independently. For multi-page work, build a content inventory, pilot the rubric, and issue per-URL decisions under `references/site-content-audit.md`. See `references/seo-ux.md`.
8. If requested, assess dependency and monetization economics using `references/book-to-engine-mapping.md`, `references/attention-quality.md`, `references/platform-dependency.md`, `references/value-capture.md`, and `references/publisher-economics.md`. Book frameworks are interpretive lenses, not Google policy.
9. If the user asks for improvement, perform a concrete edit and produce a complete revised artifact, not only recommendations. Apply `references/content-repair.md` and `references/rewrite-contract.md`; never silently invent missing evidence.
10. Re-extract all claims from the revised artifact and re-audit it, compare it with the source, calculate the score and apply hard gates. Label a same-model second pass SELF_REVIEW, never independent fact-checking. See `references/quality-gates.md`.
11. Return the revised content (or per-page patch), change log, unresolved claims and prioritized fixes; do not promise approval or a seven-day result.

## Required outputs
- Executive diagnosis with observed scope and blind spots
- Official-policy checklist: PASS / FAIL / NEEDS_REVIEW / NOT_VERIFIED, each with source URL and evidence
- Editorial score (0-100) with per-dimension evidence, separate from eligibility
- Evidence ledger and causal-argument findings for material claims
- Page-level fixes: exact location, issue, correction, validation test
- Site-level navigation, UX, crawlability and ad-placement issues
- Final decision: PUBLISH / REVISE / REJECT / INSUFFICIENT_EVIDENCE
- Optional publisher economics and measurement plan
- For repair/rewrite: full edited article or explicit page-level patches, change log, retained-thesis check, unresolved-evidence queue, and post-edit re-audit

## Hard rules
- Never invent sources, interviews, first-hand testing, data, or Google approval thresholds.
- No minimum article count, word count, domain age, traffic or approval-rate claim unless an authoritative, current source supports the exact claim.
- A page can be short and excellent or long and worthless.
- Rewrite percentage is not proof of originality.
- A strong thesis cannot excuse a false factual premise.
- Do not fabricate a personal author biography or E-E-A-T signals.
- Differentiate copyright, search spam, AdSense publisher policies, and editorial best practices.
- If no reliable evidence is available, report the gap explicitly.
- Verify current official rules when access exists; otherwise mark policy currency NOT_VERIFIED.
- No unapproved ad-click encouragement, deceptive placement, or circumvention advice.

## On-demand references
`references/adsense-policy.md`, `references/evidence-standards.md`,
`references/causal-reasoning.md`, `references/information-gain.md`,
`references/editorial-standards.md`, `references/seo-ux.md`,
`references/book-to-engine-mapping.md`, `references/publisher-economics.md`,
`references/quality-gates.md`, `references/output-contract.md`,
`references/attention-quality.md`, `references/platform-dependency.md`, `references/value-capture.md`.

## Mandatory repair behavior
If user asks to fix, upgrade, rewrite or improve provided content, do the edit now. Audit-only is insufficient. Preserve the author’s supported thesis, voice, scope, detail and intended audience unless they request otherwise. Ask for missing page text only when it is not accessible; otherwise proceed. When evidence is missing, qualify, remove or mark the affected claim rather than inventing a source. Return complete copy-ready revised content for articles and concrete before/after patches for site-wide audits. See `references/content-repair.md` and `references/rewrite-contract.md`.

## Seven-book source hierarchy
Use `references/seven-book-integration.md`. Google policy > verified source record > editorial judgment > theoretical interpretation. No inferred Google approval rule from books.

## New mandatory artifacts
For factual rewrites produce a claim ledger and preservation/change ledger. For site audits produce an inventory with coverage statement and per-URL KEEP/UPDATE/MERGE/REWRITE/REDIRECT/REMOVE/ESCALATE decision plus exact proposed patches. Separate proposed changes from applied changes.

## Mandatory report-quality checks (v6.1)
For detailed audits load guides/audit-evidence-standard.md, guides/audit-report-delivery.md and guides/blogger-indexing-safety.md. For content repair load guides/repair-and-verify.md. Findings without direct evidence must be NOT_VERIFIED. Deliver actual revised copy and re-audit it.

## Reference integrity
The `references/` directory is shipped with this repository. Resolve relative references from the repository root. For evidence-first site audits also load `guides/audit-evidence-standard.md`, `guides/audit-report-delivery.md` and `guides/blogger-indexing-safety.md`. Do not claim a real audit unless source pages were actually inspected.
