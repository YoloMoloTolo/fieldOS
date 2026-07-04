# Claude Code First Run: Agent-Reach Construction Research

This file is only for a small pipeline verification run. It is not the Fable deep-research plan.
For Fable or exhaustive Agent-Reach research, do not use the 50-100 record limit below; use
`research/fable-agent-reach-deep-research-prompt.md` and treat numeric record counts as minimum
floors, not caps.

## Start Location
Run Claude Code from:

```bash
cd /Users/ericlicona/fieldos-brain
claude
```

Agent-Reach skill is installed for Claude Code at:

```text
/Users/ericlicona/.claude/skills/agent-reach
```

## Environment State
Known working pieces as of 2026-07-04:
- Agent-Reach installed.
- Agent-Reach skill installed for Claude Code.
- OpenCLI installed.
- OpenCLI browser profile alias: `research`.
- OpenCLI connected profile previously observed as `tb7twbu4 research default`. If
  `opencli profile list` says the daemon is not running, open the research Chrome/Brave profile
  with the OpenCLI extension installed and run `PATH=/opt/homebrew/bin:$PATH opencli doctor`.
- Twitter/X works via Brave cookie extraction.
- YouTube works through `yt-dlp` after configuring `--js-runtimes node`.
- Reddit works through OpenCLI.
- Facebook and Instagram work through OpenCLI for the logged-in `research` browser profile.
- Xiaohongshu works through OpenCLI.
- LinkedIn works through `linkedin-scraper-mcp` plus `mcporter` when the local LinkedIn MCP server
  is running.
- Web/Jina Reader works.
- RSS works.
- V2EX works.
- Bilibili works.
- Exa semantic search is not configured.

Important PATH:

```bash
export PATH="/opt/homebrew/bin:$PATH"
```

Use this prefix for OpenCLI:

```bash
PATH=/opt/homebrew/bin:$PATH opencli --profile research ...
```

For LinkedIn, keep this server running in a separate terminal:

```bash
linkedin-scraper-mcp --transport streamable-http \
  --host 127.0.0.1 \
  --port 8000 \
  --path /mcp \
  --no-auto-import \
  --chrome-path "/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --user-data-dir "/Users/ericlicona/.linkedin-mcp/felix-gato-brave-profile-2~"
```

Then use:

```bash
mcporter call 'linkedin.search_jobs(keywords: "construction project manager")'
mcporter call 'linkedin.search_people(keywords: "construction contractor")'
```

## Claude Code Prompt
Paste this into Claude Code:

```text
Use the installed Agent-Reach skill.

We are in /Users/ericlicona/fieldos-brain. This repo is the research control plane.
Do not change the startup thesis based on scraped data alone.

Goal: run a first-pass construction pain-point evidence collection using Agent-Reach/OpenCLI,
then save structured artifacts under research/runs/YYYY-MM-DD-agent-reach-first-pass/.

Use only channels already working or low-friction:
- web/Jina Reader
- Twitter/X via Agent-Reach
- RSS
- V2EX if useful
- Bilibili only if relevant
- OpenCLI with --profile research for superficial Facebook/Instagram public/profile/search data

Do not use Eric's personal Facebook groups in this run.
Do not use any browser profile except OpenCLI profile "research".
Always prefix OpenCLI commands with:
PATH=/opt/homebrew/bin:$PATH opencli --profile research

Create this folder:
research/runs/YYYY-MM-DD-agent-reach-first-pass/

Create:
- manifest.md
- raw/
- evidence.jsonl
- clusters.md
- opportunities.md
- interview-questions.md
- critique.md

First, run:
agent-reach doctor --json
PATH=/opt/homebrew/bin:$PATH opencli profile list

Save the status summary in manifest.md.

Then collect 50-100 evidence records, not 500 yet. This is a pipeline test.

Search across:
- contractor payment delays
- contractor software complaints
- construction change order disputes
- construction labor shortage owner operator
- remodeling contractor problems
- home service dispatch scheduling pain
- construction permitting delays
- construction material procurement delays
- construction rework bad data
- contractor client refuses to pay
- field service technician shortage
- heat pump installer shortage
- building electrification contractor bottleneck

Evidence JSONL schema:
{
  "source_url": "",
  "platform": "",
  "source_type": "web|twitter|reddit|facebook|instagram|rss|forum|review|youtube|other",
  "speaker_role": "",
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
  "short_evidence_excerpt": "",
  "evidence_grade": "A|B|C|D"
}

Rules:
- Collection and synthesis are separate phases.
- Do not validate any thesis.
- Vendor content cannot score above C unless it cites named operator behavior or primary data.
- Prefer short excerpts over copied pages.
- Preserve URLs.
- Capture disconfirming evidence.

After collection:
1. Deduplicate records.
2. Grade evidence.
3. Produce 10-15 clusters.
4. Produce top 10 interview directions.
5. Produce top 5 buildable business opportunity areas, each with a falsifier.
6. Write critique.md attacking the evidence quality and source bias.

Stop and report what files you wrote.
```

## Follow-Up Prompt For Claude Code
After the first run:

```text
Review research/runs/YYYY-MM-DD-agent-reach-first-pass/.
Assume the clusters are wrong. Find weak evidence, missing counterexamples, source bias, and
overbuilt startup categories. Update critique.md and revise opportunities.md.
Do not update thesis/evaluation.md unless there is commitment evidence.
```

## Useful Manual Commands

Check profile:

```bash
PATH=/opt/homebrew/bin:$PATH opencli profile list
```

Facebook superficial search:

```bash
PATH=/opt/homebrew/bin:$PATH opencli --profile research facebook search "contractor problems" -f yaml
```

Instagram profile/search:

```bash
PATH=/opt/homebrew/bin:$PATH opencli --profile research instagram search "contractor" -f yaml
PATH=/opt/homebrew/bin:$PATH opencli --profile research instagram explore --limit 20 -f yaml
```

Twitter:

```bash
twitter search "contractor payment delays" --limit 20
```

Web/Jina:

```bash
curl -s "https://r.jina.ai/http://example.com"
```
