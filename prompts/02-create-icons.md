# 2. Create a matching icon set

Use this with an assistant that can produce images, either by generating them or by writing code that draws them (SVG, Python with Pillow, and so on). Drawing them in code tends to give a more consistent set, because stroke width and padding stay identical.

## Prompt

```text
Create a set of avatar icons for my Grok Bot bots. They will be shown as small circles in
a sidebar, so they must read clearly at 24 to 48 pixels.

Bots (name: job: pictogram idea):
- [Name]: [job]: [object, e.g. briefcase]
- [Name]: [job]: [object]
- [Name]: [job]: [object]

Style, applied to every icon:
- 512 x 512 PNG, one file per bot, named after the bot in lowercase (career.png).
- A rounded-square tile with a soft vertical gradient in one colour.
- One white line pictogram, centred, about 50 to 60 percent of the tile width.
- The same stroke width, line caps and corner radius in every pictogram.
- Keep the pictogram inside the central circle, so nothing is cut off when the app crops
  the tile to a circle.
- A different hue for each bot. Avoid two bots with the same colour family if their
  pictograms are similar.
- No text, letters, logos or trademarked symbols.

Also make a preview sheet (preview-sheet.png) showing:
- every icon at full size with its name underneath
- every icon circle-cropped at 48, 32 and 24 pixels, on a dark and on a light background

Then tell me which icons are hardest to tell apart at 24 pixels and suggest a fix.
```

## Checking the set

Look at the preview sheet before applying anything. At 24 pixels you should be able to say which bot is which without reading the names. Common fixes:

- Two blue tiles side by side: move one to another hue.
- A detailed pictogram (a radar with many rings, a document with many lines): drop detail until it survives at 24 pixels.
- A pictogram that touches the corners: shrink it so the circle crop doesn't clip it.

The example set in [../assets/icons/](../assets/icons/) follows these rules. Career and Email share a blue family there; the briefcase and envelope shapes keep them apart, but a different hue would make the difference clearer.
