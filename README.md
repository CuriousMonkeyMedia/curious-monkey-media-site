# Curious Monkey Media: website

This folder is the whole site, ready to publish. You don't need a build step. Open `index.html` through any static web host and it works.

## What's in here

- `index.html`: the website (all pages: About, How we work, Services, Our work, Get in touch; EN/FR)
- `support.js`: the small runtime the page needs. Keep it next to `index.html`
- `assets/`: logo, portrait, service icons, client logos, photos and videos
- `CNAME`: tells GitHub Pages to serve the site at `curious-monkeymedia.ca`

The page loads React and Google Fonts from public CDNs, so visitors need an internet connection (normal for a website).

## Put it live with GitHub Pages + your domain

1. **Create a repository** on GitHub, e.g. `curious-monkey-media-site` (Public).
2. **Upload the contents of this folder** (not the folder itself) to the repo root: `index.html`, `support.js`, `CNAME`, `README.md` and the `assets/` folder.
   - Large videos: GitHub's web uploader limits files to 25 MB each. If any `.mp4` is larger, upload with GitHub Desktop or `git` (limit 100 MB per file).
3. In the repo, go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Still in **Settings → Pages**, under *Custom domain*, enter `curious-monkeymedia.ca` and save. Tick **Enforce HTTPS** once it becomes available (can take up to 24 h).
5. **At your domain registrar** (where you bought curious-monkeymedia.ca), set DNS:
   - Four `A` records for the root domain (`@`) pointing to:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - A `CNAME` record for `www` pointing to `<your-github-username>.github.io`
   - Remove any old `A`/`CNAME` records for `@` and `www` that point elsewhere (e.g. a parked page).
   - **Keep your email (MX) records unchanged** so hello@ / daniel@ / accounts@ keep working.
6. Wait for DNS to propagate (minutes to a few hours), then visit https://curious-monkeymedia.ca.

## Handing it to Claude Code

Open this folder (or the GitHub repo) in Claude Code and give it this README. Useful asks:

- "Deploy this static site to GitHub Pages with the custom domain in CNAME."
- "Convert index.html into a Vite/React or Astro project while keeping the design pixel-identical." (Optional. The site already works as is.)
- "Compress the videos in assets/ to under 5 MB each without visible quality loss." (Recommended for faster loading on phones.)
- "Connect the contact form to a form service (e.g. Formspree) so enquiries arrive at hello@curious-monkeymedia.ca without opening the visitor's email app."

## Key details to preserve

- Contact email: `hello@curious-monkeymedia.ca`
- Booking link: https://calendar.app.google/TDFeHMnXmwJy3zsY6
- Hours: Mon–Thu 9 AM – 6 PM, Fri 9 AM – 3 PM, Sunday by appointment (Montreal time)
- Brand colours: ink `#0B0B0B`, header `#262421`, gold `#D9A81C` (hover `#E8BC3A`), text `#F2F0EB`, muted `#B9B4A8`
- Fonts: Outfit (headings), Archivo (UI), DM Sans (body), DM Mono (labels), all from Google Fonts
- Background video wall shows only on the About page and is always muted. Our work videos keep sound and controls.
- The contact form currently opens the visitor's email app with a pre-filled message to hello@. The live website previews on Our work embed the real sites, so each site must allow being framed.
