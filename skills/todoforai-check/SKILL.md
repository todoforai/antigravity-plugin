---
name: todoforai-check
description: >-
  Check the status and results of TODO for AI handoffs, answer an agent's
  question, or send a follow-up. Use when the user asks how a handed-off
  TODO is going, what it produced, or wants to reply to it.
---

## Steps
1. If the user did not give a TODO, call `list_todos` and pick the one that matches, or show the
   latest few (title, status, URL) and ask which one.
2. Call `get_todo`. Summarise `latest_reply` in a few lines, with the status and URL.
3. If `needs_user` is true, say exactly what it is waiting for. Approvals and sign-ins
   have to be done at the TODO URL. A plain question can be answered with `send_message`
   once the user gives you the answer.
4. Use `send_message` only with the user's wording or approval. Never approve on their behalf.
5. Do not poll in a loop. Check once per user request.
