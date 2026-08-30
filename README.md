# Glyph Press

A tiny, single-file web app that turns typed text into Unicode look-alike
styles — bold, italic, script, fraktur, double-struck, circled, fullwidth,
small caps, superscript, strikethrough, underline, and more — plus a
tap-to-copy kaomoji library. Everything is plain Unicode text under the
hood, so the result pastes cleanly into Messages, Notes, social apps,
anywhere.

**Live demo:** https://andrs-projects.github.io/glyph-press/

<img width="1600" height="900" alt="IMG_4480" src="https://github.com/user-attachments/assets/ef024254-644e-4ca9-9050-35ae996637fe" />


## How it works

These aren't real fonts. Each style maps ordinary Latin letters (and
sometimes digits) to their look-alike code points in Unicode blocks like
[Mathematical Alphanumeric Symbols](https://en.wikipedia.org/wiki/Mathematical_Alphanumeric_Symbols),
Enclosed Alphanumerics, and Halfwidth/Fullwidth Forms. No custom font
files are ever loaded or rendered — the "styling" is just character
substitution, which is exactly why it survives copy-paste into apps that
don't accept custom fonts.

A few styles have gaps: some blocks are missing digits, and a handful of
letters have historical "holes" in the Unicode block (filled by
older, pre-existing math symbols instead). Where no look-alike exists,
the plain character is used as a fallback.

## Using it

- Open [the live demo](https://andrs-projects.github.io/glyph-press/) in any browser, or
- Clone this repo and open `index.html` directly — it's fully
  self-contained (no build step, no dependencies beyond two Google Fonts
  loaded over the network for the display type).

On iOS or Mac Safari, the page offers to be added to your Home
Screen/Dock. Note: iOS currently ignores the custom app icon declared
here and falls back to its own default — a known platform limitation,
not a bug in this repo.

## Stack

Plain HTML/CSS/JS. No framework, no build tooling. Typography: [Fraunces](https://fonts.google.com/specimen/Fraunces),
[Public Sans](https://fonts.google.com/specimen/Public+Sans), [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono).

## License

MIT — see [LICENSE](LICENSE).
