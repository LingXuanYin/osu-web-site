# Third-party notices

This project is distributed under the terms in [LICENSE](LICENSE) (PolyForm Strict
1.0.0). That licence covers **this project's own code only**. The third-party code
listed below is covered by its own, separate, permissive licences, which are
reproduced here as those licences require. Nothing in `LICENSE` removes or narrows
any right you have in the third-party code under its own terms.

## Ported code: ppy/osu and ppy/osu-framework

osu!web ports game logic and algorithms from osu!lazer. The upstream code is MIT
licensed, which permits distributing derivative works under different terms
provided the copyright notice is retained. It is retained here.

Reference revisions this project is written against:

- `ppy/osu` @ `b11b274d1cb5c22eabe9dba5df14fa1e4ecc4e6d`
- `ppy/osu-framework` @ `2026.629.0` (`a0b031e`)

> Copyright (c) 2025 ppy Pty Ltd <contact@ppy.sh>. (ppy/osu)
> Copyright (c) 2024 ppy Pty Ltd <contact@ppy.sh>. (ppy/osu-framework)
>
> Permission is hereby granted, free of charge, to any person obtaining a copy of
> this software and associated documentation files (the "Software"), to deal in
> the Software without restriction, including without limitation the rights to
> use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
> the Software, and to permit persons to whom the Software is furnished to do so,
> subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in all
> copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
> IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
> FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
> COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
> IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
> CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

### What is deliberately NOT ported

`osu-resources` — the official skin textures, hit samples, and fonts — is **not**
MIT and is **not** used here. Every default-skin texture is generated at runtime as
an SVG data URI and every hit sample is hand-synthesised PCM. See `CLAUDE.md` for
the rule that keeps it that way.

## Bundled runtime dependencies

| Package | Licence | Copyright |
| --- | --- | --- |
| `pixi.js` | MIT | Copyright (c) 2013-2023 Mathew Groves, Chad Engler |
| `fflate` | MIT | Copyright (c) 2026 Arjun Barrett |
| `spark-md5` | WTFPL OR MIT | Copyright (C) 2015 André Cruz |
| `lzma-js-simple-v2` | MIT | Kionell |
| `onnxruntime-web` | MIT | Copyright (c) Microsoft Corporation |
| `idb-keyval` | Apache-2.0 | Jake Archibald |

The `onnxruntime-web` npm package ships without a `LICENSE` file; its MIT licence
and copyright line are taken from the upstream repository,
<https://github.com/microsoft/onnxruntime/blob/main/LICENSE>.

The MIT text above applies verbatim to each MIT-licensed package, substituting its
own copyright holder. `idb-keyval` is licensed under the Apache License 2.0; its
full text is at <https://www.apache.org/licenses/LICENSE-2.0>.

## Bundled fonts (SIL Open Font License 1.1)

The two typefaces below are bundled into the build as **unmodified** font files,
taken from the npm packages named here (`dist/assets/*.woff2`). This project does not
change any glyph. Each package declares `OFL-1.1` in its `license` field and ships the
SIL Open Font License 1.1 text in its `LICENSE` file; the full text is also at
<https://openfontlicense.org/>. Neither package's `LICENSE` contains a Reserved Font
Name clause, so no font name is reserved here. The first copyright line of each section
is copied from the package's own `LICENSE` file; the Poppins section's second line is
quoted from the upstream `OFL.txt` named there, because the upstream file carries it.

### Poppins (`@fontsource/poppins@5.3.0`)

> Copyright 2020 The Poppins Project Authors (https://github.com/itfoundry/Poppins)

The upstream `OFL.txt` (<https://raw.githubusercontent.com/itfoundry/Poppins/HEAD/OFL.txt>)
carries a different copyright line, which is kept here as well:

> Copyright 2014-2019 Indian Type Foundry (info@indiantypefoundry.com)

Used: weights 300, 400, 600 and 700, the `latin` and `latin-ext` subsets, WOFF2 only.

### Noto Sans SC Variable (`@fontsource-variable/noto-sans-sc@5.3.1`)

> Google Inc.

Used: the variable font (weight 100–900) in its 101 `unicode-range` slices, WOFF2 only.
The upstream licence at <https://raw.githubusercontent.com/notofonts/noto-cjk/main/Sans/LICENSE>
does not carry a copyright line of its own; the line above is the one the package gives.

## Bundled icon paths (Font Awesome Free 5.15.4)

Twenty-four icons are copied as SVG path data into `src/shell/icons.ts`; no npm package is
added, and no font file is bundled. The data comes from `@fortawesome/free-solid-svg-icons@5.15.4`
(and, for the regular heart, pause-circle and play-circle, `@fortawesome/free-regular-svg-icons@5.15.4`). Each entry in
`icons.ts` names its source file. The shapes are not modified; the path strings are copied
verbatim and checked against the packed originals.

Licences: icons CC BY 4.0, code MIT, fonts SIL OFL 1.1 (not used here). The attribution
below is copied from the package's `attribution.js`:

> Font Awesome Free 5.15.4 by @fontawesome - https://fontawesome.com
> License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License)

These icon paths stay under CC BY 4.0; this project's own licence does not change them.
The CC BY 4.0 text is at <https://creativecommons.org/licenses/by/4.0/legalcode>.

## Licence compatibility note

Every dependency above is permissive (MIT / Apache-2.0 / WTFPL / SIL OFL 1.1) and therefore
permits this project to be distributed under stricter terms. **Copyleft
dependencies (GPL, LGPL, AGPL, SSPL) are incompatible with this project's
licence and must not be added.** GPL-family licences require that downstream
recipients receive the right to redistribute; `LICENSE` explicitly withholds that
right. The two cannot both be satisfied.
