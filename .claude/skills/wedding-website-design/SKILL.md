---
name: wedding-website-design
description: Design system for Maria & Cole's wedding website (maria-cole-wedding.html) — colors, fonts, and spacing/border conventions. Use whenever adding or editing styles, sections, tabs, or visual elements on the site, so new work matches the existing look instead of introducing new patterns.
---

# Wedding Website Design System

This is a single-file site (`maria-cole-wedding.html`) with all CSS in the `<style>` block in `<head>`. Match these conventions instead of inventing new colors, fonts, or spacing values.

## Colors

Always use the CSS variables defined in `:root` — never hardcode a hex value that duplicates one of these:

- `--navy: #7FA7BD` — primary accent (buttons, backgrounds like `.callout`)
- `--navy-deep: #597E93` — darker accent, used for sub-headings (e.g. `color:var(--navy-deep)` on `h3` inside sections)
- `--cream: #FAFAF9` — page background
- `--cream-2: #EEF2F4` — secondary/hover background
- `--terracotta: #9FBAC9` — tag/label color
- `--rose: #4F7185` — used for `.callout.rose` variant and incorrect-answer red border
- `--gold: #A9C4D4` — highlight accent (ticket dates, Jeopardy tiles)
- `--ink: #2A3B42` — primary text color
- `--line: rgba(42,59,66,0.14)` — border color

If a new accent color is truly needed, add it as a new `--variable` in `:root` rather than a one-off hex code, and pick something in the same soft/muted blue-green family as the existing palette.

## Fonts

Three typefaces, loaded via the Google Fonts `<link>` in `<head>`:

- **Headings and titles** (`h1`, `h2`, `h3`, `.display`, and the page `<title>`): Baskerville — `'Libre Baskerville', Baskerville, 'Baskerville Old Face', serif`, weight 700. This is the single font for every heading/title across the whole site (hero title, section `h2`s, card `h3`s, modal titles, etc.) — don't mix in a different heading font for a specific tab or section. Libre Baskerville only has weights 400/700 — never use 500 or 600 on headings.
- **Body text** (default on `body`, plus inputs/buttons like `.composer input`, `.jeo-opt`): `'Helvetica Neue', Helvetica, Arial, sans-serif`.
- **Mono/eyebrow/label text** (`.mono`, `.post-meta`, tags, timers): `'Space Mono', monospace`.
- `'Fraunces', serif` (italic) is kept only for decorative accents that predate the Baskerville heading switch — the hero `&`, the Cyrillic line, ticket day numbers, Jeopardy tile values/final score. Don't extend Fraunces to new headings; use Baskerville for anything that's actually a heading or title.

If a new Google Font is ever needed, add it to the existing combined `<link href="https://fonts.googleapis.com/css2?family=...">` import rather than adding a second `<link>` tag.

## Spacing & shape

- Border radius: `8px` on small controls (inputs), `10-12px` on tiles/buttons, `16px` on cards/callouts/images.
- Cards (`.card`) and callouts (`.callout`) are the standard containers for grouped content — reuse them instead of writing bespoke `<div>` styles for new sections.
- `.callout` is navy background with cream text by default; `.callout.rose` is the alternate variant for a different tone (e.g. a warning/fun-fact aside).
- Section intros follow the `.section-head` pattern: an optional `.eyebrow.mono` label, an `h2`, and a short `<p>` description — keep this structure when adding a new tab/panel.
