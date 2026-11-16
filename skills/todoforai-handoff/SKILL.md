---
name: todoforai-handoff
description: >-
  Hand off non-coding follow-through work to a persistent TODO for AI agent:
  launch announcements, beta-user emails, social posts, outreach, form filling,
  Stripe/analytics checks, or work that must run later or on a schedule.
  Use only when the user explicitly asks to delegate, hand off, or schedule
  such work to TODO for AI.
---

## When to use
The user asked for it. Never start a TODO on your own initiative, and never
hand off coding work you can do in this workspace.

## Steps
1. Restate the handoff in one short block and get the user's OK before calling any tool:
   - **Outcome**: what "done" looks like.
   - **Destinations**: where anything gets sent or published (email list, X account, form URL).
     Default to drafts. Ask before choosing send/publish.
   - **When**: now, or a specific time. Resolve relative times ("tomorrow morning") to an absolute
     date, time and timezone, and confirm the timezone with the user.
   - **Cost**: the TODO runs on the user's TODO for AI credit (this assistant's own usage still applies).
2. Build the prompt for `run_todo`. It must stand alone, because the TODO agent cannot see
   this workspace. Include only what the task needs: release notes, product name, links,
   audience, tone. Do not include secrets, `.env` contents, tokens, or whole files.
3. Call `run_todo` with the prompt. Pass `project_id` / `agent_id` only if the user named one
   (`list_projects`, `list_agents`).
4. Reply with the TODO URL and its `todo_id` / `project_id` (needed by `todoforai-check`).
   Approvals and sign-ins happen at that URL. For scheduled work, say the schedule is
   pending until the TODO confirms it. `run_todo` starts the TODO immediately; the TODO agent
   sets up the schedule itself.

## Prompt template
```
Goal: <outcome>
Context: <product, release notes, links, audience>
Deliverables: <drafts / sent items / report>
Constraints: draft only unless I approve in this TODO; <tone, language, limits>
When: now
  | or: do not do the work now. Create a durable schedule for <YYYY-MM-DD HH:MM timezone>
    (or <recurrence>), then reply with the scheduled TODO's id, URL, time and timezone.
Report back: summary of what was done, with links.
```
