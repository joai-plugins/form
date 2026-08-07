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

- `form-create` (collect) — Create a standalone public form for lead capture, contact requests, registrations, or feedback. The form is brandless and can optionally be published in the Form store.
- `form-delete` (collect) — Permanently delete a form owned by the current team. This removes the form and its public URL.
- `form-field-add` (prompt, collect) — Add an input field to an existing form.
- `form-field-remove` (prompt, collect) — Permanently remove a field from a form.
- `form-field-update` (prompt, collect) — Update a field in an existing form.
- `form-get` (collect) — Fetch a form with its current definition, public URL, and publication status. Use it before editing fields or changing store visibility.
- `form-install` (collect) — Install a public Form store template into the current team. The installed form is brandless, publicly embeddable, and independent from the source template.
- `form-list` (collect) — List all forms owned by the current team, including brandless forms. Returns each form's definition, public URL, and publication status.
- `form-publish` (collect) — Publish a public form in the Form store so other teams can discover and install it. The original form remains owned by the current team.
- `form-unpublish` (collect) — Remove a form from the Form store while keeping its public form URL active. Existing installed copies are not affected.

## Usage Notes

- Every listed action becomes an MCP tool when the app server is connected.
- Prefer the generated provider plugin when one is available, and fall back to the raw MCP URL otherwise.

## Auth Notes

- Some actions require provider credentials or OAuth on first use.
