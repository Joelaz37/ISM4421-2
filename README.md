# Songsmith — AI Music Generator

A single-page app that generates music with the [Suno API](https://docs.sunoapi.org).

## Features
- **Simple mode**: describe a song and Suno writes the lyrics and music.
- **Custom mode**: set your own title, style tags and lyrics, with a ✨ lyrics generator.
- Instrumental toggle and model picker (V3.5 → V5).
- Advanced options: exclude styles, vocal gender, style weight, weirdness.
- Live progress, stream preview, MP3 download, cover art and lyrics view.
- Credit balance display and track history saved in the browser.

## Login
Users sign in with **Continue with Google** or with email + password via Supabase Auth
(project `New`, `bgcpvsdafecjvtqkjnmy`). After signing in, the header shows the person's
name and profile picture from `user_metadata` (`full_name` / `avatar_url`).
Includes email confirmation, forgot/reset password and sign out. Each user's Suno key
and track history are stored separately in the browser.
The Supabase client library is bundled in `public/vendor/` so no CDN is needed.

**One-time Supabase setting:** Dashboard → Authentication → URL Configuration →
set **Site URL** to your Netlify URL and add `https://YOUR-SITE.netlify.app/**` to
**Redirect URLs**. Without this, confirmation and reset emails link to `localhost:3000`
and Google sign-in won't return to your site.

**Google provider:** Dashboard → Authentication → Sign In / Providers → Google: enable it and
paste the Google OAuth client ID and secret. In Google Cloud Console, add
`https://bgcpvsdafecjvtqkjnmy.supabase.co/auth/v1/callback` as an authorized redirect URI.

## API key
Users paste their own Suno API key (from https://sunoapi.org/api-key) into the page.
It is stored only in that browser's localStorage and sent only to `api.sunoapi.org`.

## Deploy to Netlify
Connect this repo in Netlify. `netlify.toml` publishes the `public/` folder, and no build command is needed.
To run it locally, serve `public/` with any static server, for example `npx serve public`.
