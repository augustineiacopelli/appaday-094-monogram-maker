# AppADay 094 - Monogram Maker

Enter up to three initials, choose a typeface, an arrangement, a frame and a palette, then take the result away as a clean, self-contained SVG.

**Live:** https://augustineiacopelli.github.io/appaday-094-monogram-maker/
**Portfolio:** https://augustineiacopelli.github.io/appaday/

## What it does

The preview is a live 600x600 SVG built from real vector text, not a canvas rasterization. Every control redraws it immediately, and the file you download is the same markup you are looking at.

Six typefaces are on offer, from Cormorant Garamond and Playfair Display through Cinzel, Libre Baskerville, Marcellus and Josefin Sans. Four arrangements handle the usual monogram conventions: a plain row of equals, a center layout with the dominant initial enlarged in the traditional married style, an interlocked version where the letters overlap, and a vertical stack. Ten frames run from no frame at all through circle, double circle, square, rounded square, diamond, hexagon, shield, laurel arcs and an art deco cut-corner border, each available in three rule weights. Eight palettes cover ivory, navy and gold, sage, oxblood, slate and blush, midnight, forest and brass, and flat monochrome, with an option to drop the background entirely for a transparent file.

Letter placement is measured against the live document with `getComputedTextLength`, so positions are exact per glyph rather than estimated, and the layout auto-fits itself down whenever the initials would otherwise crowd the frame.

## Self-contained export

By default the export fetches a character-subset of the chosen Google Font, base64 encodes the woff2 and embeds it as an `@font-face` rule inside the SVG. The downloaded file therefore renders correctly offline, in other applications, and on machines that have never seen the typeface. If the fetch fails or embedding is switched off, the export falls back to a linked `@import` rule instead.

A copy-to-clipboard action produces the same markup for pasting straight into a project.

## Technical notes

Single-file vanilla HTML, CSS and JavaScript. No frameworks, no build step, no canvas. Google Fonts via CDN for the on-page preview. Settings persist through `localStorage` inside a try/catch. Fully ASCII source.

## AppADay

One complete, functional, mobile-friendly web app every day.
