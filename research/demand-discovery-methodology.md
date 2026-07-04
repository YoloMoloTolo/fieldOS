# Demand Discovery Methodology

## Purpose

Use internet evidence to discover construction pain points, then test demand with marketing
experiments, waitlists, interviews, and paid commitments. The goal is not to validate an idea from
scraped complaints. The goal is to rank where Eric should spend scarce interview, sales, and build
time.

## Core Thesis

Online scraping is a map of possible pain. It is not proof of demand.

Live scraped internet evidence with URLs outranks prior theses, founder intuition, model priors,
synthetic personas, summaries, and agent opinions for discovery. If live evidence contradicts the
current thesis, preserve the contradiction and let the evidence lead.

Direct non-affiliated buyer commitments outrank scraped evidence when deciding whether to build.

Demand evidence must climb this ladder:

1. Repeated public complaint from a real operator.
2. Specific past event with role, workflow, trigger, and consequence.
3. Evidence of current workaround, paid tool, manual process, dispute, delay, or lost money.
4. Direct interview confirms the same past behavior.
5. The buyer gives commitment: intro, data, pilot time, letter of intent, deposit, paid preorder,
   or paid manual concierge service.

Only levels 4-5 should influence what to build first.

## Source Quality Model

Grade every scraped record before synthesis.

### A-grade

Specific past event plus money, time, workaround, paid tool, legal risk, lost job, delayed payment,
lost margin, churn, lien, chargeback, callback, failed inspection, or repeated operational failure.

### B-grade

Specific past event with a role and context, but weak economic or commitment signal.

### C-grade

Vague complaint, preference, wishlist, secondhand story, generic social commentary, or vendor
content with no named operator behavior.

### D-grade

SEO content, AI-written listicles, vendor marketing, generic surveys with no primary detail,
engagement bait, or claims that cannot be tied to a workflow.

Do not let C/D evidence define product direction. C/D can suggest search terms only.

## Research Method

### 1. Netnographic scan

Observe naturally occurring online conversations across Reddit, Facebook, Instagram, YouTube,
LinkedIn, X, forums, job posts, reviews, public docs, and trade sources. Use this to identify:

- roles who complain unprompted
- workflows where language is emotionally intense
- moments where money/time/legal risk appears
- tools and workarounds people already use
- recurring phrases that can become ad/search copy

Preserve context. A complaint without speaker role, trigger, workflow stage, and consequence is a
weak signal.

For exhaustive Fable/Agent-Reach runs, do not impose an artificial record cap. Treat requested
record counts as floors and keep collecting while new source families, actors, workflows,
disconfirming evidence, or A/B-grade records are still appearing.

### 2. Jobs-to-be-Done translation

Translate every strong complaint into:

- actor
- job they are trying to get done
- trigger event
- current workaround
- desired outcome
- constraints
- consequence of failure

Avoid software-category labels too early. "Change order app" is a solution label. "Recover margin
when scope changes after the crew is already mobilized" is closer to a job.

### 3. Opportunity scoring

Score clusters with a weighted model:

| Dimension | Weight | Question |
|---|---:|---|
| Pain frequency | 15 | How often does this happen in the wild? |
| Pain intensity | 20 | Does it create money, time, legal, labor, safety, or reputation loss? |
| Current workaround spend | 20 | Are people already paying, hiring, spreadsheeting, texting, or fighting through it? |
| Buyer reachability | 10 | Can Eric reach these buyers directly or through online ads? |
| Wedge narrowness | 10 | Can the first version solve one painful workflow for one role? |
| Differentiation | 10 | Are incumbents weak, hated, too broad, too expensive, or misfit? |
| Timing/why now | 10 | Is there a new pressure: labor, regulation, financing, insurance, AI, electrification? |
| Legal/platform risk | -15 | Does acquisition or delivery require risky scraping, personal data, or fragile platform access? |

Do not rank by market size first. Rank by acute, reachable, monetizable pain.

### 4. Marketing signal tests

Turn top clusters into ads/landing pages only after the evidence has a clear actor and painful
workflow. Each page should test one promise, one audience, and one call to action.

Test sequence:

1. Problem-language smoke test: ad or post mirrors the pain without pitching a product.
2. Landing-page waitlist: one narrow promise, one role, one workflow, one CTA.
3. Interview conversion: waitlist signup offers a short diagnostic call.
4. Manual concierge offer: solve the workflow manually or semi-manually for money.
5. Paid preorder or deposit: only when delivery terms, refund policy, and timeline are clear.

The fastest honest signal is not a waitlist. It is a stranger giving money, data, calendar time, or
workflow access.

## Metrics

Track every experiment with:

- audience
- source channel
- pain cluster
- ad/copy variant
- impressions
- click-through rate
- landing conversion rate
- qualified lead rate
- interview booking rate
- show rate
- commitment rate
- money collected
- refund requests
- reasons for no
- exact language from replies

Separate curiosity from commitment:

- weak: likes, comments, generic email waitlist
- medium: detailed form, reply explaining recent pain, booked interview
- strong: sends documents/data, asks price, names budget, requests implementation
- strongest: pays, signs, introduces team, schedules pilot, or changes workflow

## Ethical And Legal Guardrails

- Scrape only to understand market pain; do not publish personal posts, private group content, or
  identifiable quotes without permission.
- Store short excerpts and source URLs, not full copied threads.
- Do not target ads by implying sensitive personal attributes or humiliating pain.
- Do not make performance claims the product cannot substantiate.
- If taking preorders, state what exists, what does not exist, expected delivery timing, refund
  terms, and support terms.
- Respect platform rate limits and account safety. LinkedIn and logged-in social scraping are
  useful but fragile; do not build a company whose core data source depends on violating platform
  defenses.

## Research-To-Launch Gates

### Gate 0: Online evidence

At least 50 A/B-grade records in one cluster, across at least 4 source families.

### Gate 1: Interviews

At least 10 non-affiliated interviews with specific past events, and at least 5 showing active
workarounds or paid substitutes.

### Gate 2: Marketing signal

At least 3 acquisition channels tested, and at least one narrow message produces qualified leads at
a plausible customer acquisition cost.

### Gate 3: Commitment

At least 3 non-affiliated buyers commit money, data, calendar time, or pilot access.

### Gate 4: Build

Build only the smallest workflow that converts the committed buyers. Avoid broad platform scope.

## Operating Loop

Weekly loop:

1. Collect at least 100-200 new evidence records. For exhaustive Fable runs, use the larger
   collection floors in `research/agent-reach-fable-market-research-os.md` and continue past them
   while evidence quality or source-family coverage is still improving.
2. Grade and deduplicate.
3. Update cluster scores.
4. Select 1-2 clusters for interview outreach.
5. Run 2-4 landing/ad/message tests.
6. Interview people who convert.
7. Log what would reverse the current ranking.
8. Kill or narrow one weak cluster.

## Output Artifacts

Every research run should produce:

- `manifest.md`
- `raw/`
- `evidence.jsonl`
- `clusters.md`
- `scorecard.csv`
- `ad-tests.md`
- `landing-page-briefs.md`
- `interview-questions.md`
- `commitments.md`
- `critique.md`

No product thesis graduates unless `commitments.md` has real evidence.
