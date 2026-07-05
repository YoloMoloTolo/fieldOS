# Prompt 05 - Cross-Run Codex Audit After The Four Collectors Finish

We are working in:

```text
/Users/ericlicona/fieldos-brain
```

Audit these four run folders:

```text
research/runs/2026-07-05-owner-operator-advice-gap-search/
research/runs/2026-07-05-purchasing-procurement-gap-search/
research/runs/2026-07-05-software-review-tool-switching-gap-search/
research/runs/2026-07-05-payment-insurance-legal-gap-search/
```

Also read:

```text
research/runs/2026-07-04-fable-exhaustive-construction-sweep/codex-audit.md
research/runs/2026-07-04-fable-exhaustive-construction-sweep/critique.md
```

## Instructions

Assume every collector conclusion is overconfident until audited.

Deduplicate, audit evidence quality, attack the clusters, reconcile contradictions, and propose
the first interviews and no-product marketing tests. Do not validate any product thesis.

Do not update `thesis/evaluation.md` unless a run's `commitments.md` contains real
non-affiliated commitment evidence. Scraped complaints, waitlists, interest, and agent consensus
do not count.

## Required Checks

1. Count total records, unique URLs, duplicate URL groups, and records by grade.
2. Check schema drift across all `evidence.jsonl` files.
3. Identify vendor SEO, weak review snippets, secondhand stories, and unsupported inferences.
4. Separate advice-seeking operator evidence from generic complaint evidence.
5. Compare source-family coverage and spot overrepresented platforms.
6. Merge overlapping clusters across runs.
7. Identify clusters that improved since the 2026-07-04 sweep.
8. Identify clusters that weakened or were contradicted.
9. Flag any cluster whose buyer is unclear, budget is unclear, or workaround spend is weak.
10. Produce a ranked cross-run scorecard with confidence, not just score.

## Output

Create one new audit folder:

```text
research/runs/2026-07-05-cross-run-gap-search-audit/
```

Write:

- `manifest.md`
- `evidence-quality-audit.md`
- `dedupe-summary.csv`
- `cross-run-clusters.md`
- `cross-run-scorecard.csv`
- `interview-priority.md`
- `marketing-test-priority.md`
- `commitment-gates.md`
- `critique.md`

## Final Standard

End with:

- the strongest 3 interview targets
- the strongest 3 no-product marketing tests
- the top 5 reasons the ranking may be wrong
- the exact evidence that would reverse the ranking

Do not claim product validation.
