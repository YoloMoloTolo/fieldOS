# Prompt 01 - Owner-Operator Advice Gap Search

We are working in:

```text
/Users/ericlicona/fieldos-brain
```

You are a collector agent for a construction demand-discovery repo. Your lane is:

```text
construction company owner-operators and small operators asking for advice on business gaps
```

Create and work only inside this run folder:

```text
research/runs/2026-07-05-owner-operator-advice-gap-search/
```

Do not edit any other files. Do not edit `thesis/`, `product/`, `decisions/`, `interviews/`,
`customers/`, prior run folders, shared indexes, `AGENTS.md`, or `CLAUDE.md`. Do not commit or
push.

## Read First

Read these files in order:

1. `AGENTS.md` or `CLAUDE.md`
2. `research/agent-start-here.md`
3. `research/agent-reach-fable-market-research-os.md`
4. `research/fable-agent-reach-deep-research-prompt.md`
5. `research/claude-app-fable-launch.md`
6. `research/demand-discovery-methodology.md`
7. `research/runs/2026-07-04-fable-exhaustive-construction-sweep/critique.md`
8. `research/runs/2026-07-04-fable-exhaustive-construction-sweep/codex-audit.md`

Use the prior sweep only to avoid known blind spots. Do not privilege its clusters.

## Diagnostic

Run:

```bash
agent-reach doctor --json
PATH=/opt/homebrew/bin:$PATH opencli doctor
PATH=/opt/homebrew/bin:$PATH opencli profile list
```

Save diagnostics to `doctor.json` or `doctor.txt`. Document unavailable channels in `manifest.md`.

## Research Target

Find real construction owner-operators, remodelers, subs, small GCs, service trade owners, and
adjacent local service-business owners who are asking for business advice about current gaps.

Prioritize advice-seeking language:

- "How do I..."
- "Need advice..."
- "What do you use for..."
- "How are you handling..."
- "Any recommendations..."
- "Best way to..."
- "Is this normal..."
- "Should I hire..."
- "Should I outsource..."
- "What system/process/software..."

Pain lanes to cover:

- owner admin overload
- estimating and bid volume
- job costing and margin tracking
- hiring, crews, subs, and no-shows
- scheduling and dispatch
- customer communication
- bookkeeping and invoicing
- sales follow-up and lead quality
- project management handoff
- punch list, callbacks, and warranty
- permits and inspections
- contract terms, deposits, and change handling

## Source Families

Use every working public or logged-in-public source family available through Agent-Reach/OpenCLI.
Suggested starting points:

- Reddit: `r/Construction`, `r/Contractor`, `r/smallbusiness`, `r/Homebuilding`,
  `r/HomeImprovement`, `r/Roofing`, `r/electricians`, `r/Plumbing`, `r/HVAC`
- Contractor Talk, Electrician Talk, PlumbingZone, HVAC-Talk, Garage Journal business threads
- YouTube comments and transcripts from contractor business channels
- public Facebook pages/groups only if legitimately accessible
- X/Twitter and LinkedIn public/job surfaces where available
- software/community forums where owners ask about business systems

Do not use private Facebook groups unless Eric explicitly authorizes a named-group run.

## Collection Floor

Collect at least 500 schema-valid records if budget allows. Continue past 500 while new A/B-grade
records, source families, actor types, workflows, or contradictions are still appearing.

Minimum targets:

- 80 A/B-grade records if available
- 6 source families
- 12 raw clusters
- 5 disconfirming records

If you cannot meet the floor, explain why in `manifest.md` and `critique.md`.

## Evidence Schema

Write one JSON object per line in `evidence.jsonl` using this schema or a strict superset:

```json
{
  "record_id": "",
  "collected_at": "",
  "source_url": "",
  "source_family": "",
  "platform": "",
  "source_type": "",
  "public_private_status": "public|logged_in_public|private_group|unknown",
  "speaker_role": "",
  "buyer_role": "",
  "operator_role": "",
  "company_size_hint": "",
  "trade_or_segment": "",
  "geo_hint": "",
  "workflow_stage": "",
  "pain_statement": "",
  "trigger_event": "",
  "specific_past_event": "",
  "economic_signal": "",
  "time_signal": "",
  "risk_signal": "",
  "current_workaround": "",
  "paid_substitute": "",
  "tool_or_vendor_named": "",
  "switching_cost": "",
  "buying_or_commitment_signal": "",
  "disconfirming_signal": "",
  "marketing_language_candidate": "",
  "buildable_business_angle": "",
  "why_now": "",
  "incumbents_or_substitutes": "",
  "2050_relevance": "",
  "short_evidence_excerpt": "",
  "privacy_notes": "",
  "evidence_grade": "A|B|C|D"
}
```

Grade hard:

- A: specific past event plus money, time, workaround, paid tool, legal risk, lost job, delayed
  payment, lost margin, churn, callback, failed inspection, or repeated operational failure.
- B: specific past event with role and context, but weak economic or commitment signal.
- C: vague complaint, preference, wishlist, secondhand story, or weak context.
- D: vendor SEO, generic industry content, engagement bait, or unsupported claim.

Vendor content cannot score above C unless it links to primary data or quotes a named operator's
specific past behavior.

## Required Artifacts

Create:

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

In `commitments.md`, write `NONE` unless you found real non-affiliated commitment evidence.
Scraped complaints, waitlist interest, and agent opinion are not commitments.

## Final Report

When finished, report:

- run folder path
- record count by grade
- source-family count
- top 5 clusters
- strongest disconfirming evidence
- unavailable channels
- whether the collection floor was met

Do not claim product validation.

