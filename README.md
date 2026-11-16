# TODO for AI for Antigravity

Ship the code in Antigravity. Hand off the follow-through to [TODO for AI](https://todofor.ai).

TODO for AI agents do the work that comes after the code: launch announcements,
emails to beta users, social posts, outreach, form filling, Stripe and analytics checks.
Each handoff becomes a persistent TODO that runs on TODO for AI, independently of the IDE
(subject to the devices, connections, credit and approvals it needs). View results at its link,
or ask Antigravity to check.

## Install

```sh
agy plugin install https://github.com/todoforai/antigravity-plugin
```

Then open `/plugin`, expand **todoforai**, and choose **Sign in**. You need a TODO for AI account.
If you don't have one, the sign-in page creates it.

## Use

- *"Hand off the launch: draft an announcement, a beta-user email and an X post from this release."*
- *"Hand off a check of how the launch went, scheduled for tomorrow 09:00 my time."*
- *"What is the status of my TODO for AI handoffs?"*

| Skill | What it does |
| --- | --- |
| `/todoforai-handoff` | Confirms the outcome, destinations, timing and cost with you, then starts a TODO with only the context it needs |
| `/todoforai-check` | Shows status and results, and tells you what a TODO is waiting for |

## What it can and can't do

- The skills tell the assistant to start a TODO only when you ask, to confirm the plan first,
  and to send only the context the task needs, never secrets or whole files. These are
  instructions to the model, not a technical filter: review the plan before you confirm.
- What you hand off leaves the IDE and goes to TODO for AI. TODO results come back into the IDE
  when you check them.
- The TODO runs with your saved TODO for AI agent permissions and connected services.
  Sending, publishing, approvals and sign-ins happen in the TODO, at its link. The plugin
  cannot approve anything or change agent permissions.
- Runs use your TODO for AI credit, not your Antigravity quota. See [pricing](https://todofor.ai/pricing).
- Six MCP tools: `run_todo`, `send_message`, `get_todo`, `list_todos`, `list_projects`,
  `list_agents`. None of them returns stored connector credentials.

## Uninstall and revoke

- `agy plugin uninstall todoforai` removes the plugin from Antigravity.
- Access tokens expire after one hour. Refresh tokens rotate on every use, and an old one is
  rejected. The server supports RFC 7009 revocation at
  `https://api.todofor.ai/api/auth/oauth2/revoke`.
- To cut access for every client right away, email support@todofor.ai.

## Privacy

[Privacy policy](https://todofor.ai/legal/privacy-policy) · [Terms](https://todofor.ai/legal/terms-of-service) · support@todofor.ai
