# Agent-Reach/Fable Exhaustive Construction Scout

## Purpose
Use Fable plus Agent-Reach to discover construction-industry pain signals from zero and convert
them into buildable-business hypotheses. This is not validation and not a thesis. The output is
a ranked map of interview directions, market gaps, and concrete business-development paths.

## Tool Policy
Agent-Reach is the intended capability layer. Use its channel map to reach broad internet sources:
web/Jina Reader, YouTube, RSS, Exa search, GitHub, Reddit, Twitter/X, LinkedIn, Facebook,
Instagram, and other channels when available.

Depth is prioritized over minimalism, but every source must still be graded. Logged-in or
cookie-backed channels should be tagged as higher operational risk and higher bias risk. Private
or access-controlled communities may only be used when Eric has legitimate access and the research
stores short evidence excerpts rather than bulk-copied private content.

Document unavailable channels in the manifest and compensate by expanding working adjacent source
families. Do not let an unavailable backend, such as unconfigured Exa, become a hidden narrowing
constraint.

Do not let Agent-Reach's installed skill decide the research strategy. Fable owns the research
protocol; Agent-Reach only expands collection reach.

Real scraped internet evidence with source URLs outranks all prior theses, model priors, agent
summaries, and founder intuition for discovery purposes. If live source evidence contradicts an
existing belief, preserve the contradiction and let the evidence lead. Do not impose an artificial
search cap; keep searching until budget, rate limits, or platform constraints stop the run.

## Core Instruction For Fable
You are a neutral market-signal scout. Start from zero. Do not privilege FieldOS, change orders,
rehab estimating, documentation, payments, scheduling, AI, robotics, or any prior thesis.

Find public evidence of painful, frequent, expensive, or poorly served workflows among:
contractors, specialty subs, remodelers, custom builders, production builders, service trades,
property managers, flippers, BRRRR investors, lenders, inspectors, designers, architects,
suppliers, permit expediters, homeowners interfacing with builders, and adjacent local service
companies.

Collect evidence first. Cluster later. A cluster may not be named until at least five independent
records support it or one record contains unusually strong commitment evidence.

Bias toward "what could a business actually develop": workflows where a new company could sell a
service, software-enabled service, marketplace, workflow tool, data product, financing layer,
training/certification system, managed ops layer, compliance product, or infrastructure product.

## Evidence Record Schema
```json
{
  "source_url": "",
  "source_type": "forum|reddit|review|youtube|article|docs|job_post|legal|other",
  "speaker_role": "sub|GC|remodeler|builder|flipper|lender|homeowner|supplier|inspector|designer|unknown",
  "company_size_hint": "",
  "trade_or_segment": "",
  "workflow_stage": "lead|estimate|scope|contract|permit|procurement|schedule|field_execution|change|inspection|payment|closeout|warranty|other",
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

## Evidence Grading
A: Specific past event plus money, time, workaround, paid tool, lawsuit, lien, lost job, churn,
chargeback, delayed payment, or repeated operational failure.

B: Specific past event with clear role and context, but weak money or commitment signal.

C: Vague complaint, preference, wishlist, or secondhand story.

D: Vendor SEO, generic industry content, unsourced claims, or comments that cannot be tied to a
real workflow.

Vendor content cannot score above C unless it links to primary data or quotes a named operator's
specific past behavior.

## Search Matrix
Sample evenly across actors and workflows before clustering.

Actors:
- specialty subcontractors
- remodelers
- custom home builders
- production builders
- small GCs
- service trades
- flippers and BRRRR operators
- hard-money/private lenders
- property managers
- suppliers and distributors
- inspectors and permit expediters
- homeowners who hired builders
- designers and architects

Workflows:
- lead quality and sales
- bidding and estimating
- scope definition
- contracts and deposits
- permit and inspection delays
- procurement and material substitutions
- scheduling and trade coordination
- jobsite documentation
- change handling
- payment, draws, retainage, liens
- punch lists and closeout
- warranty, callbacks, and disputes

Search phrase families:
- "lost money because"
- "contractor nightmare"
- "client refused to pay"
- "change order dispute"
- "draw request delayed"
- "subcontractor no show"
- "failed inspection"
- "permit delay"
- "material price changed"
- "Buildertrend alternative"
- "JobTread review"
- "Contractor Foreman review"
- "Procore too expensive"
- "scope creep"
- "punch list software"
- "homeowner wants extra work"
- "hard money rehab budget"
- "flipping contractor estimate"
- "construction business owners hate"
- "contractor software too expensive"
- "why contractors don't use software"
- "construction labor shortage owner operator"
- "construction AI startup problem"
- "service business dispatch scheduling pain"
- "field service technician shortage"
- "home services owner problems"
- "trade business bottleneck"
- "construction insurance claims delay"
- "construction permitting backlog"
- "construction procurement delay"
- "construction material substitution"
- "construction workforce training problem"
- "building code compliance software"
- "construction robotics adoption"
- "modular construction bottleneck"
- "prefab construction failed because"
- "net zero retrofit contractor"
- "heat pump installer shortage"
- "electrification contractor bottleneck"

Source families:
- Reddit and public forums for raw complaints.
- YouTube comments and transcripts for practitioner vocabulary.
- Software reviews for paid-tool failure modes.
- App store reviews for mobile workflow pain.
- Job postings for work companies are hiring humans to do repeatedly.
- Court/lien/payment dispute records where public and practical.
- Trade-association reports for macro pressure.
- Government data for labor, housing, safety, permitting, climate, and energy constraints.
- Investor/startup databases for crowded or underbuilt categories.
- Vendor docs and changelogs for where incumbents are moving.
- Building-code, insurance, and utility sources for 2050 constraints.

## Cluster Output
For each cluster, report:
- Name of the pain in the customer's language.
- Who feels it.
- When it happens.
- What they do today.
- Why current tools/workarounds fail.
- Evidence count by grade.
- Best three evidence records.
- Strongest disconfirming records.
- Interview questions to test it Mom-Test style.
- One data point that would kill the cluster.
- Buildable business forms: software, service, software-enabled service, marketplace, financing,
  data/API, training, compliance, infrastructure, robotics/hardware, or roll-up.
- 2050 thesis: why this problem should matter more, less, or differently over the next 25 years.
- Incumbent map and wedge hypothesis.

## Final Deliverable
Produce:
- At least 1,000 evidence records across at least 12 source families, continuing beyond 1,000 when
  new high-quality or disconfirming evidence is still appearing.
- 25-40 clusters.
- Top 15 interview directions.
- Top 10 buildable business opportunity areas.
- 50 Mom-Test questions.
- A source list with URLs.
- A "do not pursue yet" list for noisy or low-commitment themes.
- A 2050 construction-industry operating model: what the industry likely needs to become.
- A wedge-to-scale map for each top opportunity.

Do not pitch a product prematurely. You may propose business forms only after the evidence
supports a pain cluster and after naming what would falsify it. The next step is interviews,
followed by commitment tests.
