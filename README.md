# Claude Custom Color Scheme

A tiny Chrome extension that restyles **claude.ai** with your own colors and font —
no more grey, no more orange.

## How it works

claude.ai themes itself almost entirely through CSS custom properties
(`--bg-*`, `--text-*`, `--accent-*`, `--font-*`). This extension injects a
stylesheet that redefines those tokens with your palette, so the whole UI
follows automatically. No app code is modified.

## Install (Load unpacked)

1. Open `chrome://extensions` in Chrome.
2. Turn on **Developer mode** (top-right toggle).
3. Click **Load unpacked** and select this folder
   (`claude-color-scheme`).
4. Reload claude.ai. Done.

To update after editing `theme.css`: hit the ↻ refresh icon on the
extension card, then reload claude.ai.

## Customize

Open `theme.css` and edit **only the values in the `:root` block at the top** —
backgrounds, text, accent, and fonts. The rest wires your palette into Claude's
internal token names.

For a custom *web* font (not installed on your machine), add an `@import` or
`@font-face` at the very top of `theme.css`, e.g.:

```css
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap");
```

## Caveats

- Claude's class names / token names can change when Anthropic ships UI updates;
  if something stops being recolored, the token name probably changed — inspect
  the element in DevTools and add/adjust the mapping.
- This only affects your browser. It doesn't change anything for other users or
  on other devices.
