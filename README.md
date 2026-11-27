# Edge to Cloud: How a Tiny Sensor Can Save a Life

A 3D, story-driven talk for **AWS Student Community Day Kathmandu 2026**
(Saturday 28 November 2026, LBEF Campus, Maitidevi).

It follows one sensor reading, 312 cm of river water at 2 AM, from a riverbank in the hills, over LoRa to a gateway,
through AWS IoT Core, Lambda and SNS, and onto a phone in a village with no mobile signal.

Built by Peter Karki.

## Run it

It is a static site. There is nothing to install or build.

```bash
# any static server works, for example:
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` directly from disk also works in most browsers, but a server is safer.

## Host it

Upload this whole folder (keep `fonts/` and `img/` next to `index.html`) to any static host:
GitHub Pages, Netlify, Cloudflare Pages, or your own site.

For GitHub Pages: Settings, Pages, deploy from branch `main`, folder `/ (root)`.

The QR code on the last slide is generated in the browser from the address the page is loaded from,
so it always points to wherever you host it.

## Controls

| Where | What |
|---|---|
| Laptop | Arrow keys, Space, click or a presentation clicker to go forward and back |
| Laptop | `N` speaker notes and timer, `O` all slides, `F` fullscreen, `H` help |
| Phone | Swipe left or right, or use the bottom bar. The 3D scene is switched off to save battery |

The page picks the layout from the screen shape: widescreen gets the 3D presentation, portrait gets the phone reader.

## What is inside

| File | Purpose |
|---|---|
| `index.html` | All 40 slides, styles and speaker notes |
| `app.js` | The 3D world (three.js), camera story, slide controls and QR code, bundled |
| `fonts/` | Big Shoulders Display and IBM Plex, self-hosted |
| `img/` | Photos from the hills field research and the event logo |

## Credits

Built with [three.js](https://threejs.org) and [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator).
Figures on the slides come from public sources, listed at the bottom of each slide.
AWS and the Student Community Day logo belong to their owners.
