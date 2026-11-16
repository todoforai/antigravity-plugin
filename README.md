# TODO for AI plugin for Antigravity

Ship the code in Antigravity. Hand off the follow-through to [TODO for AI](https://todofor.ai).

TODO for AI agents do the work that comes after the code: launch announcements,
emails to beta users, social posts, outreach, form filling, Stripe and analytics checks.
Each handoff becomes a persistent TODO that runs on TODO for AI, independently of the IDE
(subject to the devices, connections, credit and approvals it needs). View results at its link,
or ask your coding agent to check.

## Install

Antigravity:

```sh
agy plugin install https://github.com/todoforai/antigravity-plugin
```

Then open `/plugin`, expand **todoforai**, and choose **Sign in**.

Claude Code (experimental, runtime not verified yet):

```sh
claude plugin marketplace add todoforai/antigravity-plugin
claude plugin install todoforai@todoforai
```

Then run `/mcp` and authenticate **todoforai**. You need a TODO for AI account.
If you don't have one, the sign-in page creates it.

## Use

- *"Hand off the launch: draft an announcement, a beta-user email and an X post from this release."*
- *"Hand off a check of how the launch went, scheduled for tomorrow 09:00 my time."*
- *"What is the status of my TODO for AI handoffs?"*

Antigravity: `/todoforai-handoff`, `/todoforai-check`. Claude Code: `/todoforai:todoforai-handoff`,
`/todoforai:todoforai-check`. Both also trigger from plain requests like the ones above.

| Skill | What it does |
| --- | --- |
| `todoforai-handoff` | Confirms the outcome, destinations, timing and cost with you, then starts a TODO with only the context it needs |
| `todoforai-check` | Shows status and results, and tells you what a TODO is waiting for |

## What it can and can't do

- The skills tell the assistant to start a TODO only when you ask, to confirm the plan first,
  and to send only the context the task needs, never secrets or whole files. These are
  instructions to the model, not a technical filter: review the plan before you confirm.
- What you hand off leaves the IDE and goes to TODO for AI. TODO results come back into the IDE
  when you check them.
- The TODO runs with your saved TODO for AI agent permissions and connected services.
  Sending, publishing, approvals and sign-ins happen in the TODO, at its link. The plugin
  cannot approve anything or change agent permissions.
- TODOs run on your TODO for AI credit. Your coding agent's own usage still applies. See [pricing](https://todofor.ai/pricing).
- Six MCP tools: `run_todo`, `send_message`, `get_todo`, `list_todos`, `list_projects`,
  `list_agents`. None of them returns stored connector credentials.

## Uninstall and revoke

- Uninstall: `agy plugin uninstall todoforai`, or `claude plugin uninstall todoforai@todoforai`.
  Uninstalling removes the plugin locally. It does not revoke the grant on the server.
- Access tokens expire after one hour. Refresh tokens rotate on every use, and an old one is
  rejected. Clients can revoke tokens (RFC 7009) at `https://api.todofor.ai/api/auth/oauth2/revoke`.
- To have every grant revoked on the server, contact support@todofor.ai.

## Tested

- Antigravity CLI 1.5.9: skills load, the handoff asks before starting, TODOs complete,
  status checks work, and scheduled handoffs run at the requested time.
- OAuth against production: dynamic registration with the Antigravity callback, consent,
  code exchange, refresh rotation and revocation.
- Claude Code: manifests validate. The runtime MCP connection is not verified yet.

## Privacy

[Privacy policy](https://todofor.ai/legal/privacy-policy) · [Terms](https://todofor.ai/legal/terms-of-service) · support@todofor.ai
