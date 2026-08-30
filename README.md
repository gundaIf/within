# Within

Every image carries a palette it never shows you.

**Within** finds the colours inside any image, names them after real pigments, and returns them to you. Client-side, private, no server — the image never leaves your browser.

## What it does

Drop an image — a painting, a photograph, a film still, a room you liked. Within extracts the dominant colours using median cut, matches each one to a curated vocabulary of ~150 pigment and tonal names (Burnt Sienna, Payne's Grey, Terre Verte, not `#5A6E52`), and lays them out as tall columns with the names set inside.

You can adjust the count (4–12), click any swatch to copy the hex, and export a 1080×1620 poster card for sharing.

## How the naming works

No API, no LLM. A hand-built dictionary of pigment names — sourced from oil painting, printmaking, and textile traditions — each pinned to a Lab colour coordinate. Every extracted colour is matched to its nearest pigment by perceptual distance (CIE76), with lightness and chroma modifiers (Dark, Light, Muted) applied when the match drifts. Duplicates within a palette get roman numerals (Slate Grey I, Slate Grey II), the way paint manufacturers do it.

The vocabulary was tuned to avoid two failure modes: names that sound auto-generated (*Color 7*, *Blue-Gray*) and names that sound like a candle brand (*Midnight Whisper*, *Autumn Dream*). The register is painterly, not poetic.

## Run it

Open `index.html`. That's it. One file, no build step, no dependencies.

Find other similar ones: [**deeeen.xyz/](https://deeeen.xyz/)

## Configuration

Two lines at the top of the `<script>`:

- `SITE_LABEL` — your handle or URL, printed on the exported card. Leave empty to omit.
- `COLUMN_GRADIENT` — `false` for solid columns (default), `true` to deepen each column top-to-bottom.

## Credits

Typefaces: [EB Garamond](https://github.com/georgd/EB-Garamond) and [IBM Plex Mono](https://github.com/IBM/plex), loaded from Google Fonts.

The naming approach and editorial treatment were inspired by [Meditations in Color](https://meditationsincolor.com) by Pixel Symphony.
