# 2026-07-05 Deep Gap Search Run Plan

## Purpose

Launch four isolated high-volume research agents to find construction company owner-operators,
purchasing/procurement people, and adjacent decision makers who are actively asking for advice on
specific gaps in their business.

This is a collection push, not a thesis update. The goal is to increase the quantity and quality
of operator-originated evidence before synthesis.

## Load-Bearing Assumptions

Established:

- The prior exhaustive sweep produced only 66 schema-valid records and stopped from budget, not
  evidence exhaustion.
- The repo already has a run folder contract and an evidence schema.
- Direct non-affiliated commitments remain the only evidence that can graduate a thesis.

Inference:

- Advice-seeking posts are higher-signal than generic complaints because the speaker is already
  trying to solve a gap.
- Four isolated collector runs should produce more usable evidence than one very broad run, as
  long as all agents share the same artifact contract.

Speculation:

- The most valuable new evidence will come from owner-operator admin, procurement/materials,
  tool-switching, and payment/insurance/legal advice threads.

## Do Before Launch

Use the four prompts in:

```text
research/prompts/2026-07-05-deep-gap-search/
```

Start each prompt in a separate chat in the same folder:

```text
/Users/ericlicona/fieldos-brain
```

Recommended launch order:

1. Start Chat 1 and Chat 2 first.
2. Confirm they create the correct run folders and begin writing raw outputs.
3. Start Chat 3 and Chat 4.
4. Avoid running two Reddit/OpenCLI-heavy searches at exactly the same moment if account or browser
   limits appear.

## Run Folders

Each agent may write only inside its assigned folder:

```text
research/runs/2026-07-05-owner-operator-advice-gap-search/
research/runs/2026-07-05-purchasing-procurement-gap-search/
research/runs/2026-07-05-software-review-tool-switching-gap-search/
research/runs/2026-07-05-payment-insurance-legal-gap-search/
```

No agent should edit:

```text
AGENTS.md
CLAUDE.md
product/
thesis/
decisions/
interviews/
customers/
research/runs/2026-07-04-fable-exhaustive-construction-sweep/
research/indexes/
```

No agent should commit or push. Commit only after the post-run audit.

## Shared Artifact Contract

Every run must produce:

- `manifest.md`
- `doctor.json` or `doctor.txt`
- `raw/`
- `evidence.jsonl`
- `source-family-map.csv`
- `clusters.md`
- `cluster-scorecard.csv`
- `opportunities.md`
- `interview-questions.md`
- `ad-tests.md`
- `landing-page-briefs.md`
- `commitments.md`
- `critique.md`

If a required artifact cannot be completed, the agent must still create the file and explain the
blocker inside it.

## Collection Floor

Per agent:

- 500 schema-valid records if budget allows.
- Continue beyond 500 if A/B-grade evidence, new source families, new actor types, or strong
  contradictions are still appearing.
- Minimum target of 80 A/B-grade records if the lane supports it.
- Minimum target of 6 independent source families.
- Minimum target of 12 raw clusters before pruning.
- Minimum target of 5 disconfirming records.

These are floors, not caps. If the floor is not met, the run is still useful if it documents why.

## Shared Evidence Rule

Prioritize posts where the speaker is asking for advice, recommendations, diagnosis, or process
help:

- "How do I..."
- "What do you use for..."
- "Need advice..."
- "Any recommendations..."
- "Best way to..."
- "Is this normal..."
- "Should I switch..."
- "How are you handling..."
- "What software/process/vendor..."

Generic complaints are allowed only when they include role, workflow, trigger, consequence, and
workaround.

## After All Four Runs

Use:

```text
research/prompts/2026-07-05-deep-gap-search/05-cross-run-codex-audit.md
```

The audit should deduplicate, attack evidence quality, compare clusters, reconcile contradictions,
and propose first interviews and no-product marketing tests. It should not validate a product
thesis.
