# AGENTS.md

## Cursor Cloud specific instructions

### What this repo is
This is a single-file static web app: `index.html` ("Kitsch Soulmate Finder"). There is **no** package manager, build step, backend, or database. All CSS/JS is inlined in `index.html`.

### Running the app
Serve the repo root over HTTP with any static file server, e.g. from `/workspace`:

```
python3 -m http.server 8000
```

Then open `http://localhost:8000/`. Opening `index.html` via `file://` also works, but serving over HTTP is preferred so browser audio autoplay and asset loading behave correctly.

### Non-obvious notes
- Images, background music (`Downtown Girl.mp3`), and Google Fonts are loaded from **remote** URLs (`raw.githubusercontent.com/yermigionic-web/jb/...` and `fonts.googleapis.com`). Internet access is required for art/audio/fonts to render; the page's core quiz logic still runs offline (question/answer text is hardcoded).
- Background music only starts after the first user interaction (clicking the main "touch to start" screen), due to browser autoplay policies. This is expected, not a bug.
- There is no lint/test/build tooling in this repo. "Testing" means manually driving the UI flow: main screen → touch to start → locker grid → open a character profile → TEST → answer 8 questions → view matched character result.
