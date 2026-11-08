# 1. Rename bots by function

Use this in any assistant chat. It proposes names only. You stay in charge of what gets renamed.

Before you start, write down each bot's current name and, in a few words, what you actually use it for. Go by what you use it for today, not by what the bot was set up to do months ago.

## Prompt

```text
I want to rename the bots in my Grok Bot sidebar so I can pick the right one at a glance.

Rules for the new names:
- One word if possible, two at most. Ten characters or fewer is ideal.
- Name the job, not the technology: "Email", not "Gmail Agent".
- No version numbers, no "assistant", "bot", "helper", "new", "pro".
- Different first letters where possible, so the list is easy to scan.
- Plain words a stranger would understand. No inside jokes.
- If a bot does two unrelated jobs, say so and suggest which job the name should follow.
- If two bots seem to do the same job, flag it in a separate list. Don't propose merging
  them here.

Don't rename, edit or contact any bot. Only propose.

Return:
1. A table: current name | what it does | suggested name | one alternative | note
2. A short list of possible overlaps, if any.

My bots:
- [current name]: [what I use it for]
- [current name]: [what I use it for]
- [current name]: [what I use it for]
```

## Applying the names

Pick one name per bot. Then rename each one in the way your version of the app supports: the bot's profile or settings screen, or by asking the bot in its own chat if it has an action for editing its profile. If the bot asks you to confirm, confirm it there.

A rename changes the label only. The bot keeps its chat history, memories, files and routines.

## Example

| Current name (example) | What it does | New name |
| --- | --- | --- |
| JobHunter Pro v2 | Finds roles and drafts applications | Career |
| XFeed Watcher | Summarises X and news | Radar |
| Code Helper (new) | Coding and debugging | Dev |
| Writer Assistant 2 | Drafts blog posts | Blog |
| Inbox Thing | Triage and replies | Email |
| Deep Research Bot | Long research reports | Research |

The current names are invented for this example.
