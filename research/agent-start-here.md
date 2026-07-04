# Agent Start Here - Construction Market Research

Last verified: 2026-07-04.

Read this file before any Fable, Claude Code, Codex, ChatGPT, or Agent-Reach research run.

## Current Objective

Find the most acute, frequent, expensive, reachable, and poorly served problems in construction
and adjacent builder-facing service businesses. Start from zero. Do not defend FieldOS, change
orders, estimating, documentation, payments, scheduling, AI, robotics, or any prior product idea.

The output of internet research is an evidence map, interview direction, and experiment design.
It is not product validation.

## Required Reading Order

1. `AGENTS.md` or `CLAUDE.md`
2. `research/agent-start-here.md`
3. `research/agent-reach-fable-market-research-os.md`
4. `research/fable-agent-reach-deep-research-prompt.md`
5. `research/claude-app-fable-launch.md`
6. `research/demand-discovery-methodology.md`
7. `product/legal.md`
8. `thesis/evaluation.md`

Use `research/claude-code-agent-reach-first-run.md` only for a small pipeline test. Do not use
its 50-100 record target for exhaustive Fable research.

## Truth Hierarchy

For discovery:

1. Live scraped source evidence with URL, role, workflow, trigger, consequence, and short excerpt.
2. Existing interview transcripts and indexed interview JSON.
3. High-quality secondary sources that cite primary evidence.
4. Founder intuition, prior theses, model priors, agent summaries, and synthetic personas.

For build decisions:

1. Non-affiliated buyer paid commitment, deposit, signed pilot, paid diagnostic, or preorder.
2. Non-affiliated buyer gives calendar time, workflow access, data access, or team introduction.
3. Repeated interviews with specific past events and current workarounds.
4. Scraped internet evidence.

Live internet evidence can beat old beliefs for discovery. It cannot, by itself, authorize a build.

## Search Policy

Do not impose artificial search caps. Numeric record counts are floors, not ceilings.

Fable should keep expanding across platforms, source families, actors, workflows, keywords,
geographies, and disconfirming searches until time, token, rate-limit, platform, or account-risk
constraints stop the run. If new A/B-grade records, new source families, or strong contradictions
are still appearing, continue past the requested count.

## Current Tool State

Observed working stack:

- Agent-Reach installed at `/Users/ericlicona/.local/bin/agent-reach`.
- OpenCLI installed at `/opt/homebrew/bin/opencli`.
- OpenCLI Browser Bridge profile `tb7twbu4 research default` was last observed connected.
- YouTube works through `yt-dlp` with Node JS runtime configured.
- Twitter/X works through Brave cookie extraction.
- Reddit, Facebook, Instagram, Xiaohongshu, Bilibili, V2EX, RSS, and web/Jina Reader reported
  working through Agent-Reach/OpenCLI.
- LinkedIn works through `linkedin-scraper-mcp` and `mcporter`.
- Exa semantic search is not configured.
- GitHub CLI is installed but not authenticated.
- Xiaoyuzhou is off because `ffmpeg` is missing.
- Xueqiu is warning because its logged-in cookie is not configured.

Verify instead of trusting this file:

```bash
cd /Users/ericlicona/fieldos-brain
agent-reach doctor --json
PATH=/opt/homebrew/bin:$PATH opencli doctor
PATH=/opt/homebrew/bin:$PATH opencli profile list
mcporter config list
```

If `opencli profile list` says the daemon is not running, open the research Chrome/Brave profile
with the OpenCLI extension installed, then run:

```bash
PATH=/opt/homebrew/bin:$PATH opencli doctor
PATH=/opt/homebrew/bin:$PATH opencli profile list
```

For LinkedIn, keep this server running in a separate terminal when using `mcporter`:

```bash
linkedin-scraper-mcp --transport streamable-http \
  --host 127.0.0.1 \
  --port 8000 \
  --path /mcp \
  --no-auto-import \
  --chrome-path "/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --user-data-dir "/Users/ericlicona/.linkedin-mcp/felix-gato-brave-profile-2~"
```

Useful LinkedIn probes:

```bash
mcporter call 'linkedin.search_jobs(keywords: "construction project manager")'
mcporter call 'linkedin.search_people(keywords: "construction contractor")'
```

## Default Fable Run

Use:

```text
research/fable-agent-reach-deep-research-prompt.md
```

Tell Fable:

```text
Use Agent-Reach. Run agent-reach doctor --json first. Use every working backend and document
unavailable channels. Search exhaustively across all working platforms and source families.
Treat requested record counts as minimum floors, not caps. Preserve raw outputs and write JSONL.
Do not cluster before collection. Live scraped evidence with URLs outranks prior theses and agent
opinions for discovery. Direct non-affiliated commitments outrank scraped evidence for build
decisions.
```

## Run Folder Contract

Every serious research run belongs under:

```text
research/runs/YYYY-MM-DD-short-name/
```

Required artifacts:

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

Do not update `thesis/evaluation.md` unless `commitments.md` contains non-affiliated commitment
evidence.

## Safety Boundaries

Public and logged-in-public sources are preferred. Private Facebook groups and personal-account
sources are a constrained exception, not the default exhaustive workflow. Use
`research/facebook-groups-personal-account-extraction.md` only when the private group evidence is
materially better than public evidence, and store short excerpts rather than bulk private content.

Never treat a waitlist, scraped complaint, agent consensus, or synthetic persona as validation.
