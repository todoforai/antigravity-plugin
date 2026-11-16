# TODO for AI for Antigravity

Ship the code in Antigravity. Hand off the follow-through to [TODO for AI](https://todofor.ai).

TODO for AI agents do the work that comes after the code: launch announcements,
emails to beta users, social posts, outreach, form filling, Stripe and analytics checks.
Each handoff becomes a persistent TODO that keeps running after you close the IDE and reports back.

## Install

```sh
agy plugin install https://github.com/todoforai/antigravity-plugin
```

Then open `/plugin`, expand **todoforai**, and choose **Sign in**. You need a TODO for AI account.
If you don't have one, the sign-in page creates it.

## Use

- *"Hand off the launch: draft an announcement, a beta-user email and an X post from this release."*
- *"Tomorrow at 9:00, check how the launch went and report back."*
- *"What is the status of my TODO for AI handoffs?"*

| Skill | What it does |
| --- | --- |
| `/todoforai-handoff` | Confirms the outcome, destinations, timing and cost with you, then starts a TODO with only the context it needs |
| `/todoforai-check` | Shows status and results, and tells you what a TODO is waiting for |

## What it can and can't do

- Starts a TODO only when you ask, and only after you confirm the plan.
- Sends only what the task needs. It never sends secrets, `.env` files or whole files.
- Sending, publishing, approvals and sign-ins happen in the TODO itself, at its link.
  The plugin cannot approve anything on your behalf.
- Runs use your TODO for AI credit, not your Antigravity quota. See [pricing](https://todofor.ai/pricing).
- The MCP server exposes six tools: `run_todo`, `send_message`, `get_todo`, `list_todos`,
  `list_projects`, `list_agents`. It cannot change agent permissions or read credentials.

## Revoke access

Run `agy plugin uninstall todoforai`. This removes the plugin and its stored sign-in.
Access tokens expire after one hour.

## Privacy

[Privacy policy](https://todofor.ai/legal/privacy-policy) · [Terms](https://todofor.ai/legal/terms-of-service) · support@todofor.ai
