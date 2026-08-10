# Cobblestone Stories

A mobile web walk through the geology of Nantucket's cobblestone streets.
Seven stations, ~500 million years, no app to install.

    index.html            the visitor app
    survey.html           field tool: GPS, photos, video, story text
    editor.html           desktop editor for every word in the walk
    content/stones.json   all the copy
    media/                photographs, video and audio

## Put it on the web (GitHub Pages)

From this folder:

    git init
    git add .
    git commit -m "Cobblestone Stories"
    git branch -M main
    git remote add origin https://github.com/omniscopic/Cobblestone-Stories.git
    git push -u origin main

Then on github.com: the repo -> Settings -> Pages -> Source: "Deploy from a
branch" -> Branch: main, folder: / (root) -> Save. Wait a minute or two.

Live at: https://omniscopic.github.io/Cobblestone-Stories/

Open that on your phone. Add it to your home screen and it behaves like an app.

HTTPS is what makes the camera, precise GPS and the compass work — none of
them are available over plain http, which is why a local file or a LAN address
will not do for real field testing.

## Updating it later

Replace files, then:

    git add . && git commit -m "update" && git push

Pages redeploys in about a minute. Hard-refresh on the phone if you see the
old version.

## Media

Photographs are plain files. Name them exactly as below and they appear with
no rebuild:

    media/stone-NN/wide.jpg      the standing view; also frame one of the
                                 transformation, and the Time Traveler ghost
    media/stone-NN/medium.jpg    the locator (the app draws the ring)
    media/stone-NN/macro.jpg     feeds the mineral explorer
    media/stone-NN/story.mp4     the transformation
    media/stone-NN/narration.m4a optional; a link works too

    media/walk-N-M/narration.m4a the walking chapter audio
    media/station-06/            poster.jpg, origin-map.jpg, ice-diagram.jpg,
                                 film.mp4
    media/station-07/            poster.jpg, film.mp4
    media/journey/01..07.jpg     the finale's strip
    media/shared/splash-hero.jpg the opening image
    media/shared/placeholder-narration.mp3

Station 01 is filled in as a test: the shed wide shot, the rug locator, the
rock macro, and 01TRANS as the transformation.

Video and audio can also be hosted — YouTube for films, Apple Podcasts for
narration — by pasting a link into editor.html. A local file always wins.

## Editing content

1. Edit content/stones.json directly. Permanent and publishable.
2. Or use editor.html at a keyboard and survey.html in the field. Both save
   into that browser's storage and override the files on that device only;
   "Copy everything as JSON" moves that writing back into stones.json.

Precedence: provided media beats field-survey captures. Browser text edits
beat stones.json, which beats the built-in copy.

## Map

Satellite imagery: Esri World Imagery via Leaflet. No API key, no billing.
Attribution renders on the map and must stay.
