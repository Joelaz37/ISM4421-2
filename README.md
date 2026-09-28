# Songsmith — AI Music Generator

A single-page app that generates music with the [Suno API](https://docs.sunoapi.org).

## Features
- **Simple mode**: describe a song and Suno writes the lyrics and music.
- **Custom mode**: set your own title, style tags and lyrics, with a ✨ lyrics generator.
- Instrumental toggle and model picker (V3.5 → V5).
- Advanced options: exclude styles, vocal gender, style weight, weirdness.
- Live progress, stream preview, MP3 download, cover art and lyrics view.
- Credit balance display and track history saved in the browser.

## API key
Users paste their own Suno API key (from https://sunoapi.org/api-key) into the page.
It is stored only in that browser's localStorage and sent only to `api.sunoapi.org`.

## Deploy to Netlify
Connect this repo in Netlify. `netlify.toml` publishes the `public/` folder, and no build command is needed.
To run it locally, serve `public/` with any static server, for example `npx serve public`.
