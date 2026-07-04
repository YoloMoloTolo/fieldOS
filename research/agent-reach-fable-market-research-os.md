# Agent-Reach/Fable Market Research Operating System

## Purpose

Use Agent-Reach and Fable to create a high-volume market-sensing system for construction and
adjacent service businesses, then convert the strongest signals into interviews, marketing tests,
manual offers, and paid commitments.

This operating system exists to prevent a common failure mode: turning scraped complaints into a
product thesis too early.

Truth rule: real scraped internet evidence with source URLs outranks prior theses, model priors,
synthetic personas, summaries, and agent opinions for discovery purposes. If live source evidence
contradicts the existing thesis, preserve the contradiction and let the evidence lead. Direct
non-affiliated buyer commitments still outrank scraped evidence when deciding whether to build.

## Scrutiny Of The Previous Plan

The previous plan was directionally right but incomplete.

### What Was Right

- Use online signals to discover pain language and hidden workflows.
- Grade evidence instead of treating every complaint equally.
- Convert top clusters into landing pages, interviews, and paid tests.
- Avoid building until non-affiliated buyers show commitment.

### What Was Underdeveloped

- It did not separate source families strongly enough. Ten Reddit complaints can be one community
  meme, not ten independent market signals.
- It over-weighted pain intensity. A loud pain can still be rare, unpaid, unreachable, or already
  solved.
- It did not include enough adversarial inference: for each cluster, ask why this is probably not a
  business.
- It did not specify how Fable, Agent-Reach, Claude Code, and Codex divide labor.
- It did not distinguish discovery signals, demand signals, and company-formation signals.
- It did not handle 2026 AI-agent research risks: synthetic certainty, citation drift, consensus
  bias, auto-generated social content, and platform-mediated feed distortion.

## Method Stack

Use these methods together. None is sufficient alone.

1. Netnography: observe naturally occurring online community behavior.
2. Customer Development: test business-model hypotheses outside the building.
3. The Mom Test / story-based interviews: ask about past behavior, not opinions.
4. Jobs-to-be-Done / Outcome-Driven Innovation: translate complaints into jobs and desired
   outcomes.
5. Opportunity Solution Trees: separate opportunities from solutions and test assumptions.
6. Online controlled experiments: test marketing and conversion behavior where sample sizes allow.
7. Concierge/manual MVP: test willingness to pay before software.
8. Adversarial evidence review: attack source bias, weak commitment, and overbuilt categories.
9. AI-agent assisted expansion: use AI to find blind spots and generate search directions, never to
   replace buyer evidence.

## Agent Roles

### Fable

Fable is the broad research orchestrator. It should:

- run exhaustive source sweeps with no artificial record-count cap
- call Agent-Reach channels
- save raw outputs
- normalize evidence into JSONL
- cluster pain by workflow and actor
- produce source-family coverage maps
- propose experiments

Fable should not decide what to build.

### Agent-Reach

Agent-Reach is the internet capability router. It should:

- run `agent-reach doctor --json` before each run
- route commands by active backend
- use OpenCLI `research` profile for browser-backed surfaces
- use `yt-dlp` for YouTube
- use `mcporter` LinkedIn MCP for LinkedIn
- use Jina Reader for web pages

### Claude Code

Claude Code is the research-ops and repo-discipline layer. It should:

- deduplicate records
- lint JSONL
- enforce schema
- build scorecards
- write critique files
- revise prompts
- prepare landing-page briefs and interview scripts
- prevent thesis files from changing without hard commitment

### Codex

Codex is the systems/debugging layer. It should:

- maintain setup
- audit security
- update methodology
- create analysis artifacts
- challenge assumptions
- help convert research into experiments

## Evidence Hierarchy

### Discovery Signals

These indicate where to look:

- public complaints
- tool reviews
- forum threads
- YouTube comments
- job posts
- LinkedIn role descriptions
- support docs
- social media trends
- repeated questions in communities
- competitor feature requests

Discovery signals can generate hypotheses. They do not validate demand.

### Demand Signals

These indicate meaningful interest:

- detailed waitlist signup
- reply with recent specific pain
- booked interview
- form completion with role, company size, and workflow detail
- request for pricing
- request for demo
- asks whether it integrates with current workflow
- shares documents, screenshots, or process details

Demand signals can justify more interviews and manual testing.

### Commitment Signals

These can justify building:

- paid diagnostic
- deposit
- paid preorder with clear refund terms
- signed pilot
- letter of intent with named business problem and timeline
- calendar time from decision maker and operator
- access to data/workflow needed to implement
- introduction to team or buyer group
- manual concierge engagement

Only commitment signals should graduate a product thesis.

## Source-Family Triangulation

No pain cluster is strong unless it appears across independent source families.

Source families:

- contractor/operator forums
- Reddit
- Facebook groups/pages
- Instagram/Reels comments and creator content
- YouTube videos/comments/transcripts
- LinkedIn job posts and people profiles
- X/Twitter
- software reviews and app stores
- competitor communities/support docs
- public legal/dispute/lien/permit/inspection sources
- trade associations and industry reports
- government/regulatory sources
- supplier/distributor content
- customer/homeowner complaint sites

Minimum standard for a serious cluster:

- at least 50 A/B-grade records
- at least 4 source families
- at least 2 actor types
- at least 3 named existing workarounds or substitutes
- at least 5 records with money/time/legal consequence
- at least 3 disconfirming records

## Evidence Schema V2

Every record should use this schema or a strict superset.

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

## Cluster Scorecard

Score clusters, not individual complaints.

| Dimension | Weight | Scoring Rule |
|---|---:|---|
| Specificity | 10 | Past events beat opinions. |
| Frequency | 10 | Appears repeatedly across independent sources. |
| Severity | 15 | Money, time, legal, safety, labor, or reputation loss. |
| Workaround spend | 15 | People already pay, hire, spreadsheet, text, chase, or outsource. |
| Buyer clarity | 10 | Decision maker is identifiable and reachable. |
| Operator clarity | 10 | Daily user and workflow owner are identifiable. |
| Wedge sharpness | 10 | One painful workflow for one reachable role. |
| Competition gap | 10 | Incumbents are weak, misfit, hated, too broad, or too expensive. |
| Timing | 10 | New pressure from labor, regulation, financing, insurance, AI, climate, or electrification. |
| Founder advantage | 10 | Eric has access, credibility, data, or operating insight. |
| Legal/platform risk | -20 | Penalize dependence on fragile scraping, sensitive data, or deceptive acquisition. |
| False-positive risk | -20 | Penalize meme complaints, vendor SEO, vanity waitlists, and low willingness to pay. |

Keep both score and confidence. A cluster with score 82 and confidence 0.35 is not better than a
cluster with score 70 and confidence 0.75.

## 2026 AI-Agent Research Rules

AI agents are useful for breadth, recall, and synthesis. They are dangerous for certainty.

Rules:

- Use agents to expand search terms, source families, actor maps, and disconfirming hypotheses.
- Require source URLs for every claim.
- Keep raw outputs so later agents can audit extraction quality.
- Require "why this might be wrong" for every cluster.
- Use synthetic personas only to generate hypotheses and interview questions.
- Do not count synthetic users, AI personas, or agent simulations as validation.
- Do not let agents summarize away minority pain or edge-case operators.
- Deduplicate AI-generated content and likely SEO pages.
- Prefer behavior over sentiment.

## Acquisition Experiment Ladder

### Experiment 1: Problem-Language Smoke Test

Goal: find which pain phrases resonate.

Output:

- 10-20 ad/post/message variants
- one actor per variant
- one workflow per variant
- no product claim yet

Pass:

- replies contain specific recent pain
- people correct the language with better wording
- people ask whether a solution exists

### Experiment 2: Landing Page Waitlist

Goal: test role + workflow + promise.

Rules:

- one page per cluster
- no broad platform language
- CTA is either "book diagnostic" or "join pilot list"
- collect role, company type, current workaround, urgency, and budget range

Pass:

- qualified conversion rate is strong enough to justify interviews
- at least 20% of qualified signups describe a specific recent event

### Experiment 3: Interview Conversion

Goal: verify past behavior and buying process.

Pass:

- buyer can name the last time it happened
- buyer can quantify damage
- buyer shows workaround
- buyer names who approves spend
- buyer agrees to a follow-up with artifacts/data

### Experiment 4: Manual Concierge

Goal: test value before software.

Examples:

- manually chase missing closeout docs
- manually audit change-order leakage
- manually compare bids/scopes
- manually assemble permit/inspection status
- manually reconcile invoice/draw status

Pass:

- customer pays for manual help
- customer repeats use
- customer refers another operator
- workflow reveals repeatable automation surface

### Experiment 5: Paid Preorder Or Pilot

Goal: prove commitment.

Rules:

- state what exists and what does not
- state timeline
- state refund terms
- avoid performance claims that are not substantiated
- avoid collecting unnecessary sensitive data

Pass:

- 3 non-affiliated paid commitments
- named buyer and operator
- clear first workflow
- implementation calendar access

## Fable Run Types

### Run A: Wide Source Sweep

Collection floor:

- at least 1,000 evidence records when the run budget allows
- continue beyond 1,000 when new high-quality, disconfirming, or source-family-expanding evidence
  is still appearing
- 12+ source families
- 25+ raw clusters
- 3+ disconfirming searches per major cluster

Output:

- `manifest.md`
- `raw/`
- `evidence.jsonl`
- `source-family-map.csv`
- `clusters.md`
- `cluster-scorecard.csv`
- `critique.md`

### Run B: Cluster Deep Dive

Target one cluster and collect:

- actor map
- buying committee
- workflow map
- current tools
- current manual workaround
- search/ad language
- legal/regulatory friction
- existing competitors
- disconfirming evidence

### Run C: Acquisition Design

For each top cluster:

- 3 landing-page briefs
- 10 ad variants
- 10 cold DM variants
- 10 Mom Test interview prompts
- 3 concierge offers
- one falsification plan

### Run D: Adversarial Review

Assume the top cluster is wrong. Find:

- source bias
- overrepresented communities
- missing buyer
- missing budget
- better incumbent
- legal/platform risk
- distribution weakness
- why waitlist demand could be fake

## Claude Code Review Prompt

```text
Review the latest Fable run under research/runs/.
Assume the conclusions are wrong.
Check evidence.jsonl for schema drift, duplicates, weak URLs, vendor SEO, unsupported inferences,
missing source families, missing disconfirming evidence, and false-positive demand signals.
Update critique.md and cluster-scorecard.csv.
Do not update thesis/evaluation.md unless commitments.md contains non-affiliated commitment.
```

## Fable System Prompt Addendum

```text
You are not validating a product. You are building an evidence map.

Use Agent-Reach as the internet capability router. Run agent-reach doctor --json first.
Use all working active backends and document unavailable channels. Preserve raw outputs. Save every
evidence record as JSONL. Do not impose an artificial search cap; any requested record count is a
minimum floor, not a maximum.

Real scraped internet evidence with URLs outranks prior theses, model priors, synthetic personas,
summaries, and agent opinions for discovery purposes. If scraped evidence contradicts the current
belief, keep the contradiction and let the evidence lead.

Separate:
1. observed evidence
2. inference
3. speculation
4. recommended experiment

For every cluster, include:
- best evidence
- disconfirming evidence
- source-family coverage
- false-positive risk
- buyer clarity
- current workaround spend
- marketing language candidates
- next experiment
- falsifier

Do not pitch software until the evidence supports one actor, one workflow, one painful trigger,
and one plausible buyer.
```

## References To Use

- Steve Blank, Customer Development / Lean Startup: startups search for repeatable and scalable
  business models; hypotheses must be tested outside the building.
- Rob Fitzpatrick, The Mom Test: ask about past behavior and commitments, not opinions.
- Teresa Torres, Opportunity Solution Trees: separate opportunities from solutions; use
  story-based interviews and assumption tests.
- Robert Kozinets, Netnography: online community traces can support qualitative market research,
  but require ethics, context, and interpretation.
- Anthony Ulwick, Outcome-Driven Innovation: rank unmet outcomes by importance and satisfaction.
- Clayton Christensen / JTBD: understand what customers are trying to accomplish, not product
  categories.
- David Bland and Alex Osterwalder, Testing Business Ideas: test assumptions with evidence
  strength, not confidence theater.
- Ron Kohavi et al., Online Controlled Experiments: experiments require validity, power, and
  guardrails.
- FTC advertising guidance: marketing claims must be truthful, non-deceptive, and evidence-based.
- AoIR / online community ethics: public availability is not the same as ethical reuse.
- 2025-2026 synthetic persona research: AI personas may expand hypotheses, but cannot replace
  real-world commitment signals.
