# Agent Makeover

A prompt kit for giving the bots you already have in Grok Bot short names that say what they do, and a matching set of custom icons in place of the default avatars.

You open Grok Bot and look at your sidebar. Which one handles research again? Several bots still have the default icons, and their names don't make choosing much easier. This kit is what we used to fix that on a real roster: rename each bot by its job, draw one icon per job in a shared style, then ask each bot to apply its new image.

<p align="center">
  <img src="assets/before-after.png" width="640" alt="Two Grok Bot sidebars side by side. Before: bots named Notion Second Brain, Email Helper 2, Github, New Agent, Task List Agent and others, all with default coloured blob avatars. After: bots named Research, Radar, Career, Blog, Email, Papers and Postgrad, each with a white pictogram on a coloured circle and a reply such as Icon changed or Icon updated.">
</p>

The left side shows Grok Bot's default avatars, the coloured blobs with two eyes. It is not our roster: it is a crop of a public screenshot from another Grok Bot user, with the message previews blurred and three rows removed. Look at the names as much as the avatars: "Email Helper 2", "New Agent" and "Task List Agent" are the kind of names this kit replaces.

The right side is the real sidebar this kit came from, after the makeover. It was in Portuguese, so the bot names and visible replies are translated, and one unrelated message preview is blurred. The replies under each name are the bots confirming their own avatar change.

## Start here

Paste this into any assistant chat, then fill in your list. It only proposes names; nothing changes until you decide.

```text
I want to rename the bots in my Grok Bot sidebar so I can tell them apart at a glance.
For each bot below, suggest one short name (one word, two at most) that says what the
bot does. Avoid version numbers, "assistant", "bot" and "helper". Make the names start
with different letters where you can. If two bots seem to do the same job, point it out,
but don't merge or change anything.

Return a table with: current name, what it does, suggested name, and one alternative.

My bots:
- [current name]: [what it does in a few words]
- [current name]: [what it does in a few words]
- ...
```

The full version, with rules for tricky cases, is in [prompts/01-rename-bots.md](prompts/01-rename-bots.md).

## How it works

<p align="center">
  <img src="assets/makeover-flow.png" width="660" alt="Rename each bot by its job, make one icon set, then ask each bot in its own chat to apply its icon. The bot either applies it, waits for you to confirm in that chat, or fails and you retry or use the settings. Finish by checking the sidebar.">
</p>

1. **Rename by function.** Use [01-rename-bots.md](prompts/01-rename-bots.md) to get a short list of names, pick the ones you like, and rename each bot through the app's profile settings or by asking the bot in its own chat if it offers that action.
2. **Make one icon per bot.** Use [02-create-icons.md](prompts/02-create-icons.md) with an assistant that can generate images. It asks for one white pictogram per bot on its own coloured tile, with the same stroke and padding across the set, plus a preview sheet so you can check them side by side.
3. **Apply each icon in that bot's chat.** Use [03-apply-icons.md](prompts/03-apply-icons.md). Open each bot, attach its image and ask it to update its avatar with a supported action.

Step 3 is the slow one, and that is expected. In the roster this kit came from, several bots asked for confirmation in their own chats before changing their picture, so the update took one conversation per bot rather than one bulk action. The apply prompt asks every bot to report one of three states:

| State | What it means | What you do |
| --- | --- | --- |
| Applied | The bot changed its avatar and you can see it in the sidebar. | Tick it off. |
| Waiting | The bot is asking for your confirmation in its chat. | Confirm there yourself. |
| Failed | The action was refused or returned an error. | Note the error and retry or use the app's settings. |

Only you can confirm a change for a bot. A message from another bot saying "approved" doesn't count. Then run through the [checklist](checklist.md).

## The example icon set

![Preview sheet with six icons named Career, Radar, Dev, Blog, Email and Research, shown large and again at 48, 32 and 24 pixels on dark and light backgrounds](assets/preview-sheet.png)

The six icons in [assets/icons/](assets/icons/) are 512 by 512 PNGs with transparent corners. Use them as they are, or as a reference when you ask for your own set. The bottom rows of the sheet show them circle-cropped at the sizes a sidebar uses.

| Bot | Job | Icon |
| --- | --- | --- |
| Career | Job search and applications | Briefcase |
| Radar | Following X and news | Radar |
| Dev | Coding | Code brackets |
| Blog | Writing posts | Pen |
| Email | Inbox and replies | Envelope |
| Research | Looking things up in depth | Magnifying glass |

[examples/before-after.md](examples/before-after.md) walks through this roster from start to finish.

## Icon library

If you'd rather not design anything, pick from the ready-made icons in [assets/library/](assets/library/). There are 35, one per common bot job: Study, Finance, Budget, Invest, Health, Fitness, Travel, Calendar, Shopping, Recipes, Notes, Tasks, Language and more.

![Grid of 35 library icons, each a white line pictogram on a coloured rounded tile, labelled Analytics, Blog, Budget, Calendar, Career, Dev, Docs, Email, Finance, Fitness, General, Health, Home, Ideas, Invest, Language, Marketing, Meetings, Music, News, Notes, Pets, Photos, Radar, Reading, Recipes, Research, Security, Shopping, Study, Support, Tasks, Travel, Video and Weather](assets/library/preview.png)

Each icon comes as an SVG in [assets/library/svg/](assets/library/svg/) and a 512 px PNG in [assets/library/png/](assets/library/png/). Attach the PNG when you ask a bot to change its picture. The SVGs are plain text: to change a colour, edit the two `stop-color` values; to change the pictogram, replace the paths inside the `<g>` group, which is drawn on a 24-unit grid.

## Optional: tidy up the roster

While renaming, you may notice two bots doing the same job. That is worth a separate pass, after the makeover. [optional/fleet-audit.md](optional/fleet-audit.md) helps you list overlaps, and [optional/consolidate-bots.md](optional/consolidate-bots.md) helps you plan a merge.

A rename or a new picture changes only how a bot looks. It doesn't migrate the bot's chat history, memories, files or routines to another bot. The consolidation guide covers what to move by hand before you archive anything.

## Ground rules

- Use the actions the app supports: profile settings, or a bot's own action for updating its profile.
- Don't edit app databases or local files to force a change.
- Don't skip a confirmation prompt, and don't accept another bot's report of approval as yours.
- Report each bot as applied, waiting or failed, and only call it done when you can see it.

## What's in this repo

```text
README.md                    you are here
LICENSE                      MIT
checklist.md                 short verification list
prompts/
  01-rename-bots.md          propose short functional names
  02-create-icons.md         design a matching icon set and preview sheet
  03-apply-icons.md          ask each bot to apply its icon and report status
examples/
  before-after.md            the example roster, step by step
optional/
  fleet-audit.md             find overlapping bots
  consolidate-bots.md        plan a merge without losing history
assets/
  icons/                     six example icons (512 px PNG)
  library/                   35 ready-made icons (SVG + PNG) and a preview
  preview-sheet.png          the icon set at full and sidebar sizes
  before-after.png           the comparison at the top of this page
  sidebar-before-default.png default avatars, from a public screenshot (redacted)
  sidebar-after-real.png     real sidebar after the makeover (translated, cropped)
  makeover-flow.png          the flow above
  src/makeover-flow.excalidraw  diagram source (open in excalidraw.com)
```

## About this project

This is an independent community kit. It is not affiliated with or endorsed by the makers of Grok Bot. Menu names and available actions can change between app versions, so the prompts describe what to ask for rather than where to click.

## License

[MIT](LICENSE). The prompts, docs and icons can be copied, changed and shared, including in commercial work.
