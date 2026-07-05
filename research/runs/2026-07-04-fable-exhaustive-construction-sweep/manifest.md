# Run Manifest — 2026-07-04 Fable Exhaustive Construction Sweep

- Run folder: `research/runs/2026-07-04-fable-exhaustive-construction-sweep/`
- Operator: Claude (Fable 5) via Claude Code, executing `research/claude-app-fable-launch.md` "Paste This Into Claude Or Fable" block
- Date: 2026-07-04
- Mode: zero-direction exhaustive sweep. No privileged thesis. Collect first, cluster after.

## Modification from the standard launch block (explicit, user-ordered)

**LinkedIn is intentionally skipped for this entire run.** Eric's instruction: do not run
mcporter LinkedIn probes, do not require the linkedin-scraper-mcp server, document the skip.
`agent-reach doctor` reports linkedin as "ok", but per `research/claude-app-fable-launch.md`
that report is unreliable when the local MCP server is not running — irrelevant here because
the channel is excluded by instruction, not by availability. The LinkedIn source family
(job posts, role descriptions, people search) is therefore ABSENT from this evidence set.
Compensation: job-post signal was collected from Indeed/public job boards via Jina Reader
where possible; role-description signal from forums/Reddit self-descriptions.

## Channel status at run start (see doctor.json / doctor.txt)

| Channel | Status | Backend | Used in run |
|---|---|---|---|
| Reddit | ok | OpenCLI (research profile tb7twbu4) | yes |
| Twitter/X | ok | twitter-cli | yes |
| YouTube | ok | yt-dlp | yes |
| Web pages | ok | Jina Reader (r.jina.ai) | yes |
| RSS | ok | feedparser | yes |
| Facebook | ok | OpenCLI (public surfaces only) | attempted |
| Instagram | ok | OpenCLI | attempted |
| Bilibili | ok | bili-cli | light probe |
| XiaoHongShu | ok | OpenCLI | light probe |
| V2EX | ok | public API | light probe |
| GitHub | warn (gh unauthenticated) | Jina fallback | via Jina only |
| Exa search | NOT CONFIGURED (mcporter: no local servers) | — | no — compensated with direct-URL Jina reads + platform-native search |
| Xiaoyuzhou | off (ffmpeg missing) | — | no |
| Xueqiu | warn (no cookie) | — | no |
| LinkedIn | SKIPPED BY INSTRUCTION | — | **no — intentional** |

## Privacy posture

- Public and logged-in-public surfaces only, through the OpenCLI `research` profile.
- Eric's personal Facebook groups NOT used (not authorized for this run).
- Short excerpts stored, not bulk thread content. URLs always stored.

## Run state — COMPLETE (2026-07-04)

- [x] Preflight diagnostics saved (doctor.json, doctor.txt)
- [x] Collection: Reddit — 17 searches / 14 subreddits / 12 deep-reads (42 records)
- [x] Collection: web forums — ContractorTalk + BiggerPockets via opencli web read + WebSearch (6 records)
- [x] Collection: software review sites — first-party BLOCKED (Capterra/G2/Trustpilot CDN walls); secondary review sources used (3 C-grade records)
- [x] Collection: Twitter/X — 7 queries (5 records; weak operator-pain family, documented)
- [x] Collection: YouTube — 3 searches + 2 transcripts + 1 comment pull (2 records)
- [x] Collection: RSS / news — Construction Dive (3 records); forconstructionpros 403
- [x] Collection: Facebook/Instagram — probed; FB search unparseable, IG account-search only (0 records; personal FB groups NOT used)
- [x] Collection: CN platforms — Bilibili 2 records; XHS empty; V2EX not relevant
- [x] Collection: association — AGC 2025 workforce survey (2 records); gov/legal partial via DOL-on-twitter (gap noted)
- [x] Collection: job posts — Indeed Nashville via browser (1 record; LinkedIn-substitute)
- [x] evidence.jsonl — 66 records, schema-valid, deduped (20 A / 33 B / 12 C / 1 D; 13 speaker roles)
- [x] source-family-map.csv — 10 populated + 10 skipped/blocked/probed families
- [x] clusters.md — 30 raw clusters (2 flagged under-collected)
- [x] cluster-scorecard.csv — weighted model + confidence, all 30
- [x] opportunities.md — top 10 with falsifiers + Mom-Test sets
- [x] interview-questions.md — 15 directions
- [x] ad-tests.md — 12 variants, evidence-backed clusters only
- [x] landing-page-briefs.md — 3 briefs, gated behind smoke tests
- [x] commitments.md — NONE (explicit; thesis/evaluation.md untouched)
- [x] critique.md — adversarial review incl. floor shortfall and bias analysis

## Honest constraint disclosure (final)

The methodology's 1,000-record floor was NOT met: **66 records**. The binding constraint was
the operating session's context/token budget plus browser-bridge latency — not evidence
exhaustion. New A/B-grade records were still appearing at stop time. Per doctrine this is a
legitimate stopping condition, but every downstream ranking must be read as provisional
(critique.md §1). Top-4 clusters have the deepest multi-thread support; the middle of the
ranking is budget-censored. Recommended: 1-3 continuation runs (Reddit depth, roofing/insurance
vein, first-party reviews via a non-blocked network, court/lien records) before interview
budget is committed beyond the top 4 clusters.

Tool notes for next run: Jina Reader 401-blocked from this network (AS reputation) — use
`opencli web read` + WebFetch/WebSearch; Capterra/G2 blocked even via browser reader; shell cwd
resets between calls (always `cd` absolute first); `opencli web read` is lossy on forum comment
pages; yt-dlp needs vtt (no ffmpeg); feedparser missing — stdlib XML works.
