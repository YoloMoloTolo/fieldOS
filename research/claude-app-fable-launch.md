# Claude App / Fable Launch Command

Use this when starting the exhaustive construction pain-point sweep from Claude or Fable.

## Preflight On The Mac

Run from Terminal:

```bash
cd /Users/ericlicona/fieldos-brain
agent-reach doctor --json
PATH=/opt/homebrew/bin:$PATH opencli doctor
PATH=/opt/homebrew/bin:$PATH opencli profile list
mcporter config list
```

If OpenCLI says the daemon is not running, open the browser profile that has the OpenCLI extension
installed and is logged into the research accounts, then run:

```bash
PATH=/opt/homebrew/bin:$PATH opencli doctor
PATH=/opt/homebrew/bin:$PATH opencli profile list
```

If the run will use LinkedIn, keep this running in a separate Terminal window:

```bash
cd /Users/ericlicona/fieldos-brain
linkedin-scraper-mcp --transport streamable-http \
  --host 127.0.0.1 \
  --port 8000 \
  --path /mcp \
  --no-auto-import \
  --chrome-path "/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --user-data-dir "/Users/ericlicona/.linkedin-mcp/felix-gato-brave-profile-2~"
```

## Paste This Into Claude Or Fable

```text
We are working in /Users/ericlicona/fieldos-brain.

Treat this repo as the shared research control plane for Eric, Codex, Claude, Fable, and
Agent-Reach. Read these files first, in order:
1. CLAUDE.md
2. research/agent-start-here.md
3. research/agent-reach-fable-market-research-os.md
4. research/fable-agent-reach-deep-research-prompt.md
5. research/demand-discovery-methodology.md
6. product/legal.md
7. thesis/evaluation.md

Use Agent-Reach as the internet capability router. Run:
agent-reach doctor --json
PATH=/opt/homebrew/bin:$PATH opencli doctor
PATH=/opt/homebrew/bin:$PATH opencli profile list
mcporter config list

Create a run folder:
research/runs/YYYY-MM-DD-fable-exhaustive-construction-sweep/

Write these artifacts:
- manifest.md
- doctor.json or doctor.txt
- raw/
- evidence.jsonl
- source-family-map.csv
- clusters.md
- cluster-scorecard.csv
- opportunities.md
- interview-questions.md
- ad-tests.md
- landing-page-briefs.md
- commitments.md
- critique.md

Start from zero. Do not privilege FieldOS, change orders, estimating, documentation, payments,
scheduling, AI, robotics, or any archived thesis. Search exhaustively across every working
Agent-Reach backend and adjacent public source family.

No artificial search caps. Numeric record counts are floors, not ceilings. Continue while new
A/B-grade records, source families, actors, workflows, geographies, disconfirming signals, or
high-quality contradictions are still appearing.

For discovery, live scraped internet evidence with URLs and short excerpts outranks prior theses,
founder intuition, model priors, synthetic personas, summaries, and agent opinions. For build
decisions, direct non-affiliated buyer commitments outrank scraped evidence.

Do not cluster before collection. Preserve raw outputs. Every evidence record must include source
URL, source family, speaker role, workflow stage, pain statement, trigger event, economic/time/risk
signal, current workaround, incumbent/substitute, disconfirming signal, buildable business angle,
short excerpt, privacy note, and A/B/C/D grade.

Use logged-in/public browser surfaces only through the OpenCLI research profile. Do not use Eric's
personal Facebook groups unless Eric explicitly authorizes that named-group run. Store short
excerpts, not bulk private content.

After collection:
1. Deduplicate evidence.
2. Grade source quality.
3. Produce 25-40 pain clusters.
4. Score clusters with source-family coverage, frequency, severity, workaround spend, buyer
   clarity, wedge sharpness, timing, founder advantage, legal/platform risk, and false-positive
   risk.
5. Produce top 15 interview directions.
6. Produce top 10 buildable business opportunity areas.
7. Produce disconfirming evidence and a "do not pursue yet" list.
8. Produce marketing/ad/waitlist tests only for evidence-backed clusters.

Do not update thesis/evaluation.md unless commitments.md contains real non-affiliated commitment
evidence. When finished, report the run folder path and tell Eric to ask Codex:

"Read research/runs/YYYY-MM-DD-fable-exhaustive-construction-sweep/. Deduplicate, audit evidence
quality, attack the clusters, reconcile critique, and propose the first interview and marketing
tests without validating any product thesis."
```

## Collaboration Loop

1. Fable collects and writes the run folder.
2. Claude reviews the run for weak evidence, source bias, and overbuilt categories.
3. Codex audits the artifacts, updates decisions only when a real decision was made, and keeps
   the repo consistent.
4. Eric runs interviews and commitment tests.

The repo is the shared memory. If an agent cannot see another agent directly, it collaborates by
reading and writing `research/runs/`, `decisions/log.md`, `interviews/`, and `thesis/evaluation.md`.
