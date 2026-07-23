---
name: use-form
description: Use the Form JoAi app plugin when the task needs Form tools or workflows.
---

# Form

Connect Form to Claude, Codex, and ChatGPT through JoAi's hosted MCP app server.

If a specific task was given, identify the relevant MCP tool and call it immediately — no preamble.

If invoked with no task, call the authenticate tool first (if present), then list the available actions concisely so the user can pick one.

Never ask "what would you like to do?" — either act on the task or show the menu.

## Example Prompts

- List the Form tools available in this app.
- Explain what setup or authentication Form needs before I run an action.
- Use Form to help me with the task I describe next.

## Action Inventory

- `form-create` (prompt, collect) — Create a new lead capture, RSVP, or feedback form. Returns a public link ready to share.
- `form-field-add` (prompt, collect) — Add an input field to an existing form.
- `form-field-remove` (prompt, collect) — Permanently remove a field from a form.
- `form-field-update` (prompt, collect) — Update a field in an existing form.
- `form-get` (collect) — Fetch the current definition of a form.
- `form-list` (collect) — List all forms created by your team.

## Usage Notes

- Every listed action becomes an MCP tool when the app server is connected.
- Prefer the generated provider plugin when one is available, and fall back to the raw MCP URL otherwise.

## Auth Notes

- Some actions require provider credentials or OAuth on first use.
