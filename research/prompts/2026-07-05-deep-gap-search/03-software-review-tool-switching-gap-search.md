# Prompt 03 - Software Reviews, Tool Switching, And Workflow Systems Gap Search

We are working in:

```text
/Users/ericlicona/fieldos-brain
```

You are a collector agent for a construction demand-discovery repo. Your lane is:

```text
construction operators asking whether to buy, switch, cancel, replace, or work around business software
```

Create and work only inside this run folder:

```text
research/runs/2026-07-05-software-review-tool-switching-gap-search/
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

Find construction owner-operators, PMs, estimators, admins, purchasing people, service managers,
and field leaders asking for software advice, complaining about paid tools, or describing manual
workarounds around software gaps.

Prioritize advice-seeking language:

- "Is [tool] worth it..."
- "Alternatives to [tool]..."
- "Switching from [tool]..."
- "What do you use for..."
- "Need software recommendation..."
- "How do you track..."
- "Anyone using..."
- "Why is [tool] so expensive..."
- "Canceling [tool]..."
- "Spreadsheet vs software..."

Tools and categories to probe:

- Procore
- Buildertrend
- CoConstruct
- JobTread
- ServiceTitan
- Housecall Pro
- Jobber
- Knowify
- Contractor Foreman
- CompanyCam
- Bluebeam
- PlanSwift
- STACK
- QuickBooks
- Buildern
- Monday, Airtable, Notion, Excel, Google Sheets as workarounds

Workflow lanes to cover:

- estimating and takeoffs
- bids and proposals
- project management
- schedules and dispatch
- CRM and lead follow-up
- customer communication
- documentation and photos
- change orders
- purchasing and PO tracking
- pay apps, invoicing, job costing
- closeout, punch, warranty
- integration pain with QuickBooks, accounting, email, calendar, and phones

## Source Families

Use every working public or logged-in-public source family available through Agent-Reach/OpenCLI.
Suggested starting points:

- Reddit and trade forums
- software review sites where accessible
- app store reviews
- Trustpilot, BBB, Google review snippets where accessible
- YouTube comments and transcripts
- vendor community/support forums where public
- X/Twitter public posts
- LinkedIn posts/job descriptions mentioning tool stacks
- public Facebook pages/groups only if legitimately accessible

If Capterra/G2 are CDN-walled, document that and expand adjacent source families rather than
pretending the channel was covered.

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

- A: specific past event plus money, time, paid software, implementation failure, switching cost,
  churn, workaround, lost job, lost margin, or repeated operational failure.
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

