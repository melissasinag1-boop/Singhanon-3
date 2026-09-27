# Singhanon — Offline Aklanon–English Mobile Dictionary Prototype

A lightweight, mobile-friendly web app that works as an offline-style Aklanon–English dictionary. Built with plain HTML, CSS, and JavaScript — no build tools or frameworks needed.

## Files

- `index.html` — the app (Dictionary, Saved Words, and About tabs)
- `style.css` — styling
- `app.js` — search, favorites, and report logic
- `data.js` — the dictionary entries. **Add new words here.**

## How to put this on GitHub Pages

1. Create a new repository on GitHub (e.g. `singhanon`).
2. Upload all four files (`index.html`, `style.css`, `app.js`, `data.js`) and this `README.md` to the repository root — either by dragging them into the GitHub web upload page, or with git:
   ```
   git init
   git add .
   git commit -m "Initial Singhanon prototype"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/singhanon.git
   git push -u origin main
   ```
3. In the repository, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`. Save.
5. GitHub will give you a live link, usually:
   ```
   https://YOUR-USERNAME.github.io/singhanon/
   ```
   It can take a minute or two to go live the first time.

## Adding new dictionary entries (expanding the database)

Open `data.js` and add a new object to the `DICTIONARY_ENTRIES` array, following the pattern of the entries already there:

```js
{ word: "bulak", pos: "n", definition: "Flower.", page: 60 },
```

Only `word`, `pos`, and `definition` are required. The app checks every entry when it loads and silently skips anything malformed (missing word, blank definition, etc.), logging a warning in the browser console — so a typo in one entry will never crash the whole app for your evaluators.

## Notes on this prototype

- **Favorites and reports are stored in the browser only** (`localStorage`), per device — there is no shared server backend. This fits an offline-first prototype; if your study later needs a synced backend, that would be an added feature.
- Entries are adapted from Salas Reyes, V., Zorc, R. D. P., & Prado, N. (1969). *A Study of the Aklanon Dialect, Volume Two: Dictionary (of Root Words and Derivations), Aklanon to English.* Peace Corps. (ERIC ED145704). The current dataset covers a selection of entries and is designed to be expanded.
