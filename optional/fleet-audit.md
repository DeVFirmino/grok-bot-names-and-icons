# Optional: audit the roster

Do this after the makeover, if renaming showed you bots that overlap. It only produces a list. Nothing gets merged, archived or deleted.

## Prompt

```text
Here is the list of bots in my Grok Bot sidebar, with what I use each one for and roughly
how often. Help me spot overlap.

For each bot, tell me:
- its main job in one line
- any other bot that does the same or a very similar job
- whether it looks unused, based on what I told you

Then list possible groups of bots that could share one job, with the reason. Mark each
group as "clear overlap" or "maybe". Don't suggest deleting anything, and don't contact or
change any bot.

My bots:
- [name]: [what I use it for]: [daily / weekly / rarely / never]
- [name]: [what I use it for]: [daily / weekly / rarely / never]
```

## Reading the result

A "clear overlap" is two bots you would ask the same question. A "maybe" is often two bots that look similar but keep different context, such as one coding bot per project. Leave those alone unless switching between them annoys you.

If you want to merge a group, go to [consolidate-bots.md](consolidate-bots.md).
