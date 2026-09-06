# theagent47.com

Public marketing site for the Agent 47 AI Receptionist. Served by GitHub Pages
at **https://theagent47.com**.

Static: one HTML file plus media. No build step, no dependencies.

| File | |
| --- | --- |
| `index.html` | The whole site — markup, CSS and JS inline |
| `*.mp4` | Background films for the hero and three sections |
| `*-poster.jpg` | First-frame stills, shown until each clip is ready |
| `og.jpg` | 1200×630 link-preview card |
| `CNAME` | Custom domain for GitHub Pages — do not delete |

## Working on it locally

```bash
python3 -m http.server 8000
```

Open a real server rather than the file directly — `file://` blocks the video
loads.

## Notes

- **Media is referenced as separate files, not inlined.** An earlier version
  embedded everything as base64 for a preview environment that blocked external
  files; that made the page 1.9 MB. As separate files it is ~44 KB and the clips
  load lazily and cache. Keep it this way.
- **`preload="none"` on the three section clips** means a visitor only downloads
  one when they scroll to it. Only the hero preloads.
- **Nothing is hidden by CSS that JS is expected to reveal.** The headings and
  the flow diagram set their own initial state in script, so the page renders
  complete without JavaScript.
- Fonts are Doto and Space Mono from Google Fonts — the only external requests.

The receptionist's source lives in a separate private repository.
