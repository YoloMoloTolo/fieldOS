# Personal Facebook Groups Extraction Runbook

## Purpose
Extract research signals from Facebook groups that Eric can legitimately access through his
personal Facebook account, while keeping the blast radius smaller than "let an agent roam through
my whole personal browser."

This is a higher-risk workflow than public web, Reddit, YouTube, RSS, or Brave-cookie extraction.
Use it only when the target group content is materially more valuable than public sources.

This runbook is a risk-governed exception to the exhaustive Fable workflow. The general Fable rule
is no artificial search cap. Private or personal-account Facebook group extraction is different:
the goal is targeted, high-signal sampling without exposing Eric's whole personal account, copying
private communities in bulk, or triggering account defenses.

## Non-Negotiable Boundary
There is no clean way for OpenCLI/Agent-Reach to read private or member-only Facebook groups
without a browser session logged into an account that can see those groups.

If the groups are only visible to Eric's personal Facebook account, then any automated extraction
must use a Chrome/OpenCLI profile logged into that personal account.

## Recommended Setup
Create a separate Chrome profile named:

```text
Eric FB Research
```

In that profile:
- Log into Eric's personal Facebook account.
- Install the OpenCLI extension.
- Do not log into banking, email, iCloud, or unrelated personal accounts.
- Keep this Chrome profile separate from day-to-day browsing.

Then bind OpenCLI to that profile:

```bash
PATH=/opt/homebrew/bin:$PATH opencli doctor
PATH=/opt/homebrew/bin:$PATH opencli profile list
PATH=/opt/homebrew/bin:$PATH opencli profile rename CONTEXT_ID personal_fb
PATH=/opt/homebrew/bin:$PATH opencli profile use personal_fb
```

Replace `CONTEXT_ID` with the real connected profile id.

Always run Facebook commands with:

```bash
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb ...
```

Never rely on the default profile.

## Group URL Workflow
For each group, manually open the group in the `Eric FB Research` Chrome profile first. Confirm
that posts are visible.

Then use an OpenCLI browser session against the visible page:

```bash
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup bind
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup state
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup extract
```

If the group is not already open, use:

```bash
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup open "FACEBOOK_GROUP_URL" --window foreground
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup wait time 5
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup extract
```

Scroll for the next batch:

```bash
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup scroll down
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup wait time 2
PATH=/opt/homebrew/bin:$PATH opencli --profile personal_fb browser fbgroup extract
```

Do not scrape endlessly. Capture small windows of high-signal posts, then stop.

## Evidence Schema
Convert each useful observation into JSONL:

```json
{
  "platform": "facebook",
  "source_type": "private_group_visible_to_account",
  "group_name": "",
  "group_url": "",
  "post_url": "",
  "date_seen": "",
  "speaker_role": "sub|GC|remodeler|builder|homeowner|supplier|unknown",
  "trade_or_segment": "",
  "pain_statement": "",
  "trigger_event": "",
  "economic_signal": "",
  "time_signal": "",
  "current_workaround": "",
  "tool_or_vendor_named": "",
  "buying_or_commitment_signal": "",
  "disconfirming_signal": "",
  "short_evidence_excerpt": "",
  "evidence_grade": "A|B|C|D",
  "privacy_note": "short excerpt only; no bulk copied private thread"
}
```

## What To Store
Store:
- Source URL.
- Group name.
- Short excerpt.
- Your structured interpretation.
- Evidence grade.
- Why it matters for interviews.

Do not store:
- Full private threads.
- Full member names unless necessary and public/professional.
- Screenshots of sensitive personal posts.
- Contact lists or member lists.

## Research Protocol
Use Facebook groups to generate interview directions, not validation.

For each group, collect:
- 10-30 high-signal evidence records unless Eric explicitly approves a deeper, named-group run
  after reviewing account, privacy, and platform risk.
- At least 3 disconfirming or "this is not a real pain" records if available.
- The language contractors use, not startup vocabulary.

Then ask Codex to cluster:

```text
Read the Facebook group evidence JSONL. Deduplicate, grade, and cluster pain signals.
Flag privacy-sensitive records. Produce interview questions, not product conclusions.
```

## Kill Switches
Stop the run if:
- Facebook shows account checkpoint or suspicious-activity warning.
- OpenCLI starts interacting outside the target group/page.
- The extraction includes member lists or unrelated personal data.
- The same group produces mostly memes, arguments, or low-commitment complaints.
- The evidence is no better than public sources.
