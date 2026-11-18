---
name: todoforai-handoff
description: >-
  Hand off work that comes after the code to a TODO for AI agent: launch
  announcements, emails to users, social posts, outreach, form filling,
  Stripe or analytics checks, or anything that should run later or on a
  schedule. Use only when the user asks to hand off, delegate or schedule
  work with TODO for AI.
---

Start a TODO only when the user asks for one. Coding work in this workspace stays with you.

## Steps

1. Settle the timing: now, or an exact date, time and timezone. Turn "tomorrow morning" into a
   real time, and ask about the timezone if it isn't clear.
2. Write the prompt for `run_todo` (template below). The TODO agent can't see this workspace,
   so the prompt has to stand on its own. Put in only what the task needs: release notes,
   product name, links, audience, tone. Leave out secrets, `.env` contents, tokens and whole files.
   Default to drafts; sending or publishing only if the user said so.
3. Show the user the exact prompt and say it runs on their TODO for AI credit. Wait for their OK.
   If you change the prompt afterwards, show it again.
4. Call `run_todo` with that prompt. Pass `project_id` or `agent_id` only if the user named one
   (`list_projects`, `list_agents`).
5. Share the returned link and keep `todo_id` and `project_id` for later checks. Approvals and
   sign-ins happen at that link. For scheduled work, this is the setup TODO: the schedule is
   pending until it reports the scheduled TODO's link and time.

## Prompt template

```
Goal: <what done looks like>
Context: <product, release notes, links, audience>
Deliverables: <drafts, sent items or a report>
Constraints: drafts only unless I approve in this TODO; <tone, language, limits>
When: <one of>
  Start now.
  Don't do the work now. Create a second TODO scheduled for <date and time or recurrence,
  with timezone>, then reply with its id, link and scheduled time.
Report back: what you did, with links.
```
