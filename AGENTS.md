# Construction venture — problem-first charter

## What we are doing
Searching for the most acute, frequent, expensive, and poorly-served problem in the construction
value chain that Eric is uniquely positioned to solve. OBSESSED WITH THE PROBLEM, FLEXIBLE ON THE
SOLUTION (Uri Levine, "Fall in Love with the Problem, Not the Solution"). YC's "Make Something
People Want" exists because lack of market need is the #1 cause of startup death (CB Insights).
The job is to find that need — not to defend a product.

## NOT YET DECIDED — do not assume any of this
- The solution FORM: software/SaaS, hardware, service, marketplace, or none of these
- The ICP / customer segment
- Pricing, features, business model, or name ("FieldOS" is a placeholder, not a commitment)
Everything in thesis/ and product/ is a FALSIFIABLE HYPOTHESIS, not a plan — a lead to test or
kill. If you catch me treating a feature or product as decided, stop me and redirect to the
underlying problem and the evidence for it.

## Fixed facts — Eric's unfair advantages (these bias the SOLUTION not at all)
- Operates two real construction businesses: Trim Design by N&R (specialty carpentry sub) and
  LGC International (remodeling)
- Some jobsite data, some sub/GC relationships, lives these workflows daily.
- ME + robotics background (Boston Dynamics, Amazon Robotics).
These give reach to customers and ground truth. They do NOT tell us what to build.

## Method (heavyweight, non-negotiable)
- Interviews = The Mom Test (Rob Fitzpatrick): talk about their LIFE, not our idea; ask about
  specifics in the PAST, not opinions about the future; talk less, listen more. Compliments,
  fluff, and feature-requests are misleading data. Hunt for COMMITMENT — time, money, and
  workarounds already spent — not interest. Opinions are worthless.
- Frame findings as Jobs To Be Done (Levitt, "Marketing Myopia," 1960; Christensen, HBR 2005,
  milkshake study): the customer hires something to make progress. Chase the OUTCOME, not the
  artifact. Quarter-inch hole, not quarter-inch drill.
- Get out of the building (Steve Blank): a hypothesis is worthless until tested on real customers.

## The gate, read correctly
Three NON-AFFILIATED paying customers. Not validation of a product — evidence that a real,
monetizable problem exists and that strangers (who, unlike Eric's own businesses, have no reason
to flatter him) will pay to solve it. Affiliated revenue can't falsify, so it doesn't count.
It is the Mom Test applied to the company itself.

## Constraints (verified truth, not assumptions)
@product/legal.md

## Evidence base (this is what we reason from; it grows over time)
- interviews/  -> indexed transcripts, the primary data
- customers/profiles.md  -> synthesized ICP signal
- decisions/log.md  -> decisions + the reversing condition for each

## Research agent startup protocol
Before any internet research, Fable run, Agent-Reach run, or Claude/Codex synthesis pass, read:
- research/agent-start-here.md
- research/agent-reach-fable-market-research-os.md
- research/fable-agent-reach-deep-research-prompt.md
- research/claude-app-fable-launch.md
- research/demand-discovery-methodology.md

Use `research/claude-code-agent-reach-first-run.md` only for a small pipeline verification run.
Do not use its 50-100 record target for exhaustive Fable research.

Fable/Agent-Reach doctrine:
- Start from zero; do not privilege archived theses.
- Search exhaustively across all working source families.
- Treat numeric record counts as minimum floors, not caps.
- Live scraped internet evidence with URLs outranks prior theses, founder intuition, model priors,
  synthetic personas, summaries, and agent opinions for discovery.
- Direct non-affiliated buyer commitments outrank scraped evidence for build decisions.
- Do not update thesis/evaluation.md unless commitments.md contains non-affiliated commitment
  evidence.

## Current hypotheses (UNPROVEN — to falsify, not assume)
@thesis/evaluation.md

## Write-back protocol
- New interview -> /index-interview -> interviews/YYYY-MM-DD-name.json
- Decision -> decisions/log.md (date, decision, rationale, reversing condition)
- Hypothesis status change -> thesis/evaluation.md
- End of session -> git add -A && git commit -m "..." && git push
