# Oika

A platform for place-based and perception-based experiences.
One brand, one structure, many titles.

Static site — no build step, no server, no keys.

## Layout

```
index.html                          Oika home — the catalogue
w/cobblestone-stories/              Title 01 — Nantucket geological walk
  index.html                        the walk itself
  content/stones.json               the words; edit this to change the walk
  media/stone-01…07/                photographs and video per stone
tools/survey.html                   Field Survey — capture GPS and reference shots on location
tools/editor.html                   Story Editor — write and revise the seven stones
.nojekyll                           tells GitHub Pages to serve every file as-is
```

Each new title becomes a new folder under `w/`. The home page links to it.
Nothing else moves.

## Publishing

1. Upload the contents of this folder to the repo root of `omniscopic/Oika`.
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `/ (root)` → Save.
3. A minute later the site is live at `https://omniscopic.github.io/Oika/`
   and the walk at `https://omniscopic.github.io/Oika/w/cobblestone-stories/`.

To update, replace the changed files and commit. Pages redeploys itself.

## Media

The walk looks for these and quietly skips any that are missing, so it can
go live before the shoot is finished:

```
w/cobblestone-stories/media/stone-01/wide.jpg      the street, for context
w/cobblestone-stories/media/stone-01/medium.jpg    the stone in its setting
w/cobblestone-stories/media/stone-01/macro.jpg     the surface, close
w/cobblestone-stories/media/stone-01/story.mp4     Rich speaking, 60–120s
```

Keep each video under about 15 MB. Visitors watch outdoors, on cellular,
often with two bars. GitHub Pages has a soft 1 GB limit on the whole repo —
if the videos outgrow it, move them to a separate media repo or a video host
and point the paths there.

## Notes

- Field Survey stores captures in localStorage on the phone that took them.
  Full-resolution photographs stay in the camera roll by design.
- The map uses Esri World Imagery via Leaflet. No API key, no billing account.
