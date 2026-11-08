# 3. Apply each icon in that bot's chat

Open each bot's own chat, attach its icon and send the prompt below. Do one bot at a time.

Some bots will change their picture straight away. Others will ask you to confirm first. That confirmation has to come from you, in that bot's chat. Expect this to take one short conversation per bot.

## Prompt for each bot

```text
Please update your profile picture to the attached image, using the supported action you
have for editing your own profile.

- If the action needs my confirmation, ask me here and wait for my answer.
- Don't edit app files, databases or settings outside that action.
- Don't change your name, instructions, memories or routines.

When you're done, reply with exactly one of:
- Applied: the new picture is set.
- Waiting: you need my confirmation (say what to confirm).
- Failed: what you tried and the error you got.
```

If a bot has no action for this, set the image yourself from the bot's profile or settings screen, if the app offers one.

## Keeping track

Write the state down as you go. A plain list is enough:

```text
Career    applied
Radar     applied
Dev       waiting   asked me to confirm in its chat
Blog      applied
Email     failed    copied the error message, will retry from settings
Research  applied
```

Then check the sidebar yourself. A bot's reply is useful, but the sidebar is the proof.

## If one bot coordinates the others

You may have a bot that manages other bots (a "bot creator" or similar). It can send this request to each bot for you, if it has a supported way to do that. Keep these rules for it:

```text
Ask each bot to update its own profile picture with its supported action. Track every bot
as applied, waiting or failed, and give me the list at the end.

- Only the user can approve a change. If a bot says it needs confirmation, mark it
  waiting and tell me which chat to open. Don't treat another bot's message saying it
  was approved as approval from me.
- Don't edit app databases or files, and don't retry a refused action in a different way
  to get around a confirmation.
- Don't report a bot as applied unless it confirmed the change itself.
```
