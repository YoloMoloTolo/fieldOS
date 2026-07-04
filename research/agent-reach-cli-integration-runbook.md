# Agent-Reach CLI Integration Runbook

## Purpose
Install Agent-Reach as a user-level internet capability layer, then use FieldOS as the research
control plane for Fable, Codex, Claude Code, and chat-based synthesis.

Agent-Reach should not be cloned into this repository. Its config, tools, cookies, and upstream
repos belong under `~/.agent-reach/`. This repo stores the research protocol and outputs.

## Current Local Preflight
Current verified state from `/Users/ericlicona/fieldos-brain` as of 2026-07-04:
- `agent-reach` is installed at `/Users/ericlicona/.local/bin/agent-reach`.
- `pipx` is installed at `/opt/homebrew/bin/pipx`.
- OpenCLI is installed at `/opt/homebrew/bin/opencli`.
- OpenCLI extension is installed and was last observed connected.
- OpenCLI profile `tb7twbu4 research default` was last observed connected.
- YouTube works through `yt-dlp` after configuring `--js-runtimes node`.
- LinkedIn works through `linkedin-scraper-mcp` plus `mcporter` when the LinkedIn MCP server is
  running locally.
- Agent-Reach most recently reported 11/15 channels active, including Twitter/X, Reddit,
  Facebook, Instagram, Xiaohongshu, Bilibili, V2EX, RSS, web/Jina Reader, YouTube, and LinkedIn.
- Exa semantic search is not configured.
- GitHub CLI is installed but not authenticated.
- Xiaoyuzhou is off because `ffmpeg` is missing.
- Xueqiu is warning because its logged-in cookie is not configured.
- The shell resolved `node` to `/opt/homebrew/bin/node` v26.4.0 in the latest verification.

Use `PATH=/opt/homebrew/bin:$PATH` for OpenCLI/Node-based commands if a shell falls back to an
older Node or cannot find Homebrew tools.

If `opencli profile list` says the daemon is not running, open the research Chrome/Brave profile
with the OpenCLI extension installed, then run `PATH=/opt/homebrew/bin:$PATH opencli doctor`.

Recommended persistent PATH fix:

```bash
echo 'export PATH="/opt/homebrew/bin:/opt/homebrew/sbin:$PATH"' >> ~/.zshrc
exec "$SHELL" -l
which node
node --version
```

Expected: `which node` should resolve to `/opt/homebrew/bin/node`.

## Install Path A — Recommended macOS User-Level Install
Use this when you want Agent-Reach available from any shell, including inside FieldOS.

```bash
cd /Users/ericlicona/fieldos-brain

if ! command -v brew >/dev/null 2>&1; then
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  eval "$(/opt/homebrew/bin/brew shellenv)"
fi

brew install python@3.12
brew install pipx
pipx ensurepath
exec "$SHELL" -l

pipx install https://github.com/Panniantong/agent-reach/archive/main.zip
agent-reach --help
```

Then preview the install:

```bash
agent-reach install --env=auto --dry-run
```

Then install core channels:

```bash
agent-reach install --env=auto
agent-reach doctor
```

Core channels should include web/Jina Reader, YouTube, RSS, V2EX, and basic Bilibili, depending
on upstream availability. Exa requires separate `mcporter` configuration. GitHub requires `gh auth
login` for authenticated operations.

## Install Path B — Virtualenv Fallback
Use this if you install Python 3.12 but do not want `pipx`.

```bash
cd /Users/ericlicona/fieldos-brain

python3.12 -m venv ~/.agent-reach-venv
source ~/.agent-reach-venv/bin/activate
python -m pip install --upgrade pip
python -m pip install https://github.com/Panniantong/agent-reach/archive/main.zip

agent-reach --help
agent-reach install --env=auto --dry-run
agent-reach install --env=auto
agent-reach doctor
```

For future shells:

```bash
source ~/.agent-reach-venv/bin/activate
```

## Optional Channels
After core install, add only the channel families needed for the research run.

High-reach research install:

```bash
agent-reach install --env=auto --channels=opencli,reddit,twitter,facebook,instagram,linkedin,bilibili
agent-reach doctor
```

Maximum install:

```bash
agent-reach install --env=auto --channels=all
agent-reach doctor
```

Important: cookie-backed and browser-session-backed channels should be treated as high-access
research tools. Use dedicated accounts where practical.

## FieldOS Directory Contract
Keep the repo as the control plane:

```text
research/
  fable-agent-reach-deep-research-prompt.md
  agent-reach-cli-integration-runbook.md
  runs/
    YYYY-MM-DD-agent-reach-sweep/
      manifest.md
      doctor.txt
      evidence.jsonl
      sources.csv
      clusters.md
      opportunities.md
      interview-questions.md
      critique.md
```

Agent-Reach owns:

```text
~/.agent-reach/
  config.yaml
  tools/
```

Fable owns collection runs. Codex owns normalization, repo memory, and synthesis. Claude Code owns
second-pass implementation or adversarial review.

## Cooperation Architecture
```text
Fable + Agent-Reach
  collect broad internet evidence
  output JSONL records

Codex
  writes schemas and manifests
  dedupes evidence
  grades source quality
  clusters pain signals
  updates research docs and decisions

Claude Code
  independently reviews clusters
  attacks weak evidence
  runs alternate source searches
  helps build scripts or dashboards

Chat
  human-facing strategic reasoning
  interview planning
  decision discussion
```

## First Run Workflow
Create a run folder:

```bash
mkdir -p research/runs/$(date +%F)-agent-reach-sweep
```

Copy the Fable prompt:

```bash
cat research/fable-agent-reach-deep-research-prompt.md
```

In Fable, paste that prompt and tell it:

```text
Use Agent-Reach. Write results as JSONL using the schema. Search exhaustively across all working
channels. Produce at least 1,000 evidence records when the run budget allows, and continue beyond
that if new source families, actors, workflows, disconfirming signals, or A/B-grade records are
still appearing. Do not treat any numeric count as a cap.

Real scraped internet evidence with URLs outranks prior theses, model priors, summaries, and agent
opinions for discovery purposes. If scraped evidence contradicts our existing beliefs, preserve the
contradiction and let the evidence lead.

Do not cluster until after collection. Save or export the raw evidence as evidence.jsonl.
```

After Fable exports results, place them in:

```text
research/runs/YYYY-MM-DD-agent-reach-sweep/evidence.jsonl
```

Then ask Codex:

```text
Read research/runs/YYYY-MM-DD-agent-reach-sweep/evidence.jsonl.
Deduplicate, grade evidence, cluster pain signals, find disconfirming evidence, and produce
clusters.md, opportunities.md, interview-questions.md, and critique.md.
```

Then ask Claude Code:

```text
Review the same run folder. Assume Codex overfit the evidence. Find weak clusters, missing
counterexamples, source-bias problems, and overbuilt startup categories.
Write critique.md.
```

Finally, Codex reconciles:

```text
Merge the critique into the cluster rankings. Update decisions/log.md only for actual decisions.
Do not validate a thesis without commitment evidence.
```

## Direct CLI Examples After Install
### Fix Brave Cookie Extraction
If `agent-reach configure --from-browser brave` says cookie extraction requires `rookiepy` or
`browser_cookie3`, install the dependency into Agent-Reach's pipx venv:

```bash
pipx inject agent-reach rookiepy
```

If `rookiepy` fails with a PyO3/Python 3.14 compatibility error, use the quick fallback:

```bash
pipx inject agent-reach browser-cookie3
```

Then close Brave and run:

```bash
agent-reach configure --from-browser brave
```

If macOS asks for Brave keychain access, choose `Allow`, not `Always Allow`.
If it asks for Chrome Safe Storage, choose `Deny`.

Cleaner fix if `rookiepy` is required: rebuild Agent-Reach under Python 3.12, because `rookiepy`
does not currently support the Python 3.14 pipx venv used by Homebrew's latest pipx:

```bash
pipx uninstall agent-reach
pipx install --python /opt/homebrew/bin/python3.12 https://github.com/Panniantong/agent-reach/archive/main.zip
pipx inject agent-reach rookiepy
agent-reach configure --from-browser brave
```

This removes and recreates the Agent-Reach pipx app environment. It should not remove
`~/.agent-reach/config.yaml`.

Doctor:

```bash
agent-reach doctor
agent-reach doctor --json
```

Web via Jina Reader:

```bash
curl -s "https://r.jina.ai/http://example.com"
```

GitHub:

```bash
gh repo view owner/repo
gh search repos "construction technology AI permitting"
```

YouTube:

```bash
yt-dlp --dump-json "YOUTUBE_URL"
```

Reddit via OpenCLI, if installed and authenticated:

```bash
opencli reddit search "construction contractor payment delays" -f yaml
```

Facebook / Instagram via OpenCLI, if installed and authenticated:

```bash
opencli facebook search "construction contractor pain points" -f yaml
opencli instagram search "contractor" -f yaml
```

Exa via mcporter:

```bash
mcporter config list
```

LinkedIn via mcporter:

Run this server in a separate terminal and keep it open:

```bash
linkedin-scraper-mcp --transport streamable-http \
  --host 127.0.0.1 \
  --port 8000 \
  --path /mcp \
  --no-auto-import \
  --chrome-path "/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --user-data-dir "/Users/ericlicona/.linkedin-mcp/felix-gato-brave-profile-2~"
```

Then probe:

```bash
mcporter call 'linkedin.search_jobs(keywords: "construction project manager")'
mcporter call 'linkedin.search_people(keywords: "construction contractor")'
```

Important: the working LinkedIn user-data directory includes the trailing `~`.

Check `agent-reach doctor --json` for the active backend before relying on a command.

## Operating Rules
- Collection and synthesis are separate phases.
- Evidence records must include source URL, speaker role, pain, workaround, economic/time signal,
  disconfirming signal, buildable business angle, and evidence grade.
- Vendor content cannot score above C unless it contains primary evidence.
- Online complaints are not validation.
- A business direction becomes serious only after non-affiliated commitment evidence.
- Decisions go to `decisions/log.md` with a reversing condition.
