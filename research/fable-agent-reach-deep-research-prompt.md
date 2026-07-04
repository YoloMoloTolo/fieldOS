# Paste-Ready Fable Prompt: Agent-Reach Deep Construction Research

Use Agent-Reach as your internet capability layer:
https://github.com/Panniantong/agent-reach?tab=readme-ov-file

Goal: perform exhaustive internet research into what anyone online is saying about construction
industry pain points and adjacent service-business needs. The purpose is to identify what a
business could actually develop to help build the best version of the construction industry for
2050.

Start from zero. Do not privilege FieldOS, change orders, rehab estimating, documentation,
payments, scheduling, AI, robotics, or any prior thesis. Collect evidence first, then cluster.

Non-negotiable evidence priority: real internet evidence scraped from live sources, with URLs and
short excerpts, outranks prior theses, founder intuition, model priors, synthetic personas,
summaries, and agent opinions. If the scraped evidence contradicts the existing thesis, believe the
scraped evidence for discovery purposes and record the contradiction. Direct non-affiliated buyer
commitments still outrank scraped evidence when deciding whether to build.

Do not artificially limit search breadth or depth. Keep expanding across platforms, source
families, actors, workflows, keywords, and disconfirming searches until the available time, token,
rate-limit, or platform constraints are exhausted. Any numeric record count below is a minimum
floor, not a cap.

Use Agent-Reach channels where available:
- web/Jina Reader
- Exa search
- YouTube captions/transcripts and comments where accessible
- RSS
- GitHub/public docs
- Reddit
- Twitter/X
- LinkedIn
- Facebook/Instagram public or legitimate-access surfaces
- software review sites and app stores
- public forums
- public trade-association, government, insurance, lending, permitting, utility, and code sources

Document unavailable channels in the manifest and compensate by expanding working adjacent source
families. Do not let an unavailable backend, such as unconfigured Exa, become a hidden narrowing
constraint.

Research actors:
- specialty subcontractors
- remodelers
- custom and production builders
- small and mid-size GCs
- service trades
- property managers
- real estate investors, flippers, and BRRRR operators
- hard-money/private lenders
- suppliers and distributors
- inspectors and permit expediters
- designers and architects
- homeowners interfacing with builders
- adjacent local service companies

Research workflows:
- lead quality and sales
- estimating, bids, and takeoffs
- scope definition
- contracts, deposits, and financing
- permitting and inspections
- procurement, substitutions, supply-chain friction
- scheduling, dispatch, trade coordination
- field execution, labor productivity, quality control
- safety, training, certification
- documentation and proof of work
- changes and disputes
- payment, draws, retainage, collections, liens
- punch lists, closeout, warranty, callbacks
- insurance, claims, compliance, legal risk
- energy retrofit, electrification, climate resilience, building performance
- robotics, prefab, modular, offsite, 3D printing, industrialized construction

For every evidence record, output JSONL with this schema:

```json
{
  "source_url": "",
  "source_type": "forum|reddit|review|youtube|article|docs|job_post|legal|government|association|social|other",
  "speaker_role": "sub|GC|remodeler|builder|flipper|lender|homeowner|supplier|inspector|designer|service_business|unknown",
  "company_size_hint": "",
  "trade_or_segment": "",
  "workflow_stage": "",
  "pain_statement": "",
  "trigger_event": "",
  "economic_signal": "",
  "time_signal": "",
  "current_workaround": "",
  "tool_or_vendor_named": "",
  "buying_or_commitment_signal": "",
  "disconfirming_signal": "",
  "buildable_business_angle": "",
  "why_now": "",
  "incumbents_or_substitutes": "",
  "2050_relevance": "",
  "short_evidence_excerpt": "",
  "evidence_grade": "A|B|C|D"
}
```

Evidence grading:
- A: specific past event plus money, time, workaround, paid tool, lawsuit, lien, lost job, churn,
  chargeback, delayed payment, or repeated operational failure.
- B: specific past event with role and context, but weak money or commitment signal.
- C: vague complaint, preference, wishlist, or secondhand story.
- D: vendor SEO, generic industry content, unsourced claims, or comments not tied to a real
  workflow.

Vendor content cannot score above C unless it links to primary data or quotes a named operator's
specific past behavior.

Collection floor:
- At least 1,000 evidence records if the run budget allows; continue beyond 1,000 when new source
  families, actors, workflows, geographies, disconfirming evidence, or high-grade records are still
  appearing.
- At least 12 distinct source families.
- At least 25 raw pain clusters before pruning.
- Capture disconfirming evidence, not just complaints.

After collection, produce:
- 25-40 pain clusters with evidence counts by grade.
- Top 15 interview directions.
- Top 10 buildable business opportunity areas.
- For each top opportunity: wedge, buyer, first painful workflow, why now, why 2050, incumbent
  alternatives, what would falsify it, and 5 Mom-Test interview questions.
- A "do not pursue yet" list for noisy, low-commitment, overbuilt, or legally fragile themes.
- A source appendix with URLs.

Do not pitch a product until the evidence supports a cluster. Do not treat scraped complaints as
validation. The purpose is to decide who to interview, what to ask, and what business forms are
worth testing.
