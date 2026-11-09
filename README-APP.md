# DGS Bollx — the consensus board

Third phone app alongside Sandstorm and The Holy Grail (plus Jacobs Ladder).

What it does, every time it's opened:
1. Pulls the day's published picks live from all three apps (GitHub Pages data
   files are CORS `*`, so the phone does the join directly — no server needed):
   - Sandstorm: `jobsaboba.github.io/wonderland/data/<day>.json` — `races[].sel`
   - Holy Grail: `jobsaboba.github.io/holy-grail/data/<day>.json` — top-3 ranked runners
   - Jacobs Ladder: `jobsaboba.github.io/jacobs-ladder/data/<day>.json` — `finals`
2. Joins on normalised course | time | horse.
3. Medals the horses:
   - 🏆 **Gold cup** — picked by all three apps (even bigger chance of winning)
   - 🥈 **Silver** — two apps
   - 🥉 **Bronze** — appears on any single app
4. Shows a WIN/PLACE/LOSE badge when one of the sources already knows the result.

Days shown: the last four (the same window the launcher settles each morning).

## Publishing / changing

App shell repo: `jobsaboba/dgs-bolx` → GitHub Pages.
Edit `index.html` / `sw.js` / `manifest.webmanifest`, bump `APP_VER` in
index.html **and** the `CACHE` name in sw.js, commit + push — then
force-close and reopen the app on the phone (or add the home-screen icon
from `https://jobsaboba.github.io/dgs-bolx/`).
