# orbitalsunrise.cc

The watch site for **Orbital Sunrise**, a music video about Alexei Leonov's first spacewalk and the hand-flown landing of Voskhod-2. One static page: the film, the lyrics, a close-up still of the math in his head, and the math behind "fifteen hundred klicks".

Orbital Sunrise. Song and lyrics by Jade Wang. Narrative arc inspired by John Green's essay “Orbital Sunrise” (The Anthropocene Reviewed).

The film's code (every frame drawn in colored pencil by JavaScript) and the detailed working notes live in [jadeqwang/orbital-sunrise-video](https://github.com/jadeqwang/orbital-sunrise-video).

## The film

The film is embedded from YouTube. Set its video id (the part after `watch?v=`) in the one constant near the top of the `<script>` in `index.html`:

```js
const YOUTUBE_ID = '';
```

While it is empty, the frame shows the poster still with "Film coming soon" and the lyrics are plain text. Once it is set, the page loads the YouTube player (privacy-enhanced, youtube-nocookie.com), and tapping a lyric line plays the film from that line, with the sung line lighting up as it plays.

No video files are kept in this repo.

## Deploy

It is a plain static site: `index.html` and `img/`, no build step.

Cloudflare Pages: connect this repo, framework preset "None", build command empty, build output directory `/`. Any other static host (GitHub Pages, Netlify, S3) works the same way: serve the repo root.

To preview locally: `python3 -m http.server` in the repo root, then open http://localhost:8000.
