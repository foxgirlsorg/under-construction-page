# foxgirls.org — Under Construction Page

Static holding page served while the main site was being built. Single HTML file, no framework, no build step.


## Stack

Vanilla HTML, CSS, and inline JavaScript. Fonts (Mukta Light and Mukta Regular) are self-hosted.

## Ionicons

Icons are loaded via [Ionicons](https://ionic.io/ionicons). At the time this page was made, the Ionicons CDN API was down — so rather than resolving icons by name from their servers as intended, the SVGs are bundled locally under `assets/ionicons/svg/` and the full Ionicons runtime is vendored alongside them.

This is janky. The intended workflow is a single CDN `<script>` tag; instead there's a pile of minified Stencil runtime files, a SystemJS polyfill, and hand-copied SVGs to work around the outage. If you're reusing this and the Ionicons API is back up, the entire `assets/ionicons/` directory can be replaced with one script tag.

## Structure

```
assets/
  css/style.css          — styles
  fonts/                 — self-hosted Mukta font files
  ionicons/              — vendored Ionicons runtime + local SVGs
  media/
    bg.gif               — background animation
    song.mp3x            — background music
index.html
```

## Usage

Static page — no build step required.

```bash
npx serve .
# or
python3 -m http.server
# or whatever http server you have
```


## License

MIT License — see [LICENSE](LICENSE) for details.
