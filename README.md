# Hani AlKarrain — Portfolio

Personal portfolio site. Static HTML + CSS, no build step, no dependencies.

## Files

```
hani-portfolio/
├── index.html      ← the page structure & all your content
├── styles.css      ← all styling
├── images/         ← all images, referenced by filename
└── README.md       ← this file
```

No JavaScript, no frameworks. Fonts are loaded from Google Fonts.

---

## Working on it locally

1. Open the `hani-portfolio` folder in VS Code.
2. Install the **Live Server** extension (by Ritwick Dey).
3. Right-click `index.html` → **Open with Live Server**.
4. Every time you save a file, the browser auto-refreshes.

---

## Adding your real images

The `images/` folder has 20 labeled placeholders. Each one shows the filename, section tag, and the target pixel dimensions. **Just replace any placeholder with a real image of the same name.** You don't need to touch the HTML at all.

### Image list (filename → what it is → target size)

**Featured games (4:3, ~1200×900):**
- `couch-party.jpg` — Couch Party! (Steam)
- `3d48.jpg` — 3D48 (App Store)
- `arcade-racer.jpg` — Tamatem arcade racer

**Itch library (4:3, ~800×600):**
- `assembly.jpg` — Assembly / خط التجميع
- `bubbleguard.jpg` — Bubbleguard tower defense
- `polydoor.jpg` — Polydoor puzzle platformer
- `trial-run.jpg` — Trial Run combat platformer
- `separated.jpg` — Separated puzzle
- `under-30-minutes.jpg` — Ludum Dare 53 entry
- `geared-up.jpg` — GMTK jam entry
- `day-night-farmer.jpg` — Mini Jam 101
- `electric-fields.jpg` — Field visualizer
- `game-of-life.jpg` — Conway's
- `sorting-algorithms.jpg` — Algorithm visualizer
- `15-puzzle.jpg` — Classic 15 puzzle

**Music section:**
- `music-wide.jpg` — big wide banner (2:1, ~1200×600) — good for an album cover, Spotify artwork, or studio photo
- `music-1.jpg` — square (1:1, ~800×800) — could be piano, French Horn, or a release cover
- `music-2.jpg` — square (1:1, ~800×800) — same deal

**Off the desk (16:10, ~1200×750):**
- `volleyball.jpg` — any volleyball action shot or team photo
- `cubing.jpg` — a cube, a solve, a timer — whatever you've got

### Image tips
- JPG for photos, PNG if you need transparency.
- Compress with [tinypng.com](https://tinypng.com/) before committing — aim for under ~300KB per image.
- Images are cropped with `object-fit: cover`, so focal point matters more than exact dimensions. Keep the subject near the center.

---

## Editing the text

All copy lives in `index.html`. Search for any phrase you want to change and edit it directly. Key spots:

- **Intro headline** — the "I'm a musician…" line is in the `<section class="intro">` block near the top.
- **Music section** — the three `<p>` paragraphs inside `<div class="music-main">`.
- **Game descriptions** — blurbs inside each `<a class="feat">` (featured) or `<a class="lib-item">` (library).
- **Off-the-desk** — inside the two `.desk-card` blocks.
- **Awards** — each `<div class="trophy">` inside the wall-of-gold section.
- **Footer links** — at the very bottom, before `</body>`.

---

## Deploying to GitHub Pages (free)

1. **Create a GitHub account** if you don't have one.

2. **Create a new repository.** Public. Name it something like `portfolio` — or for the cleanest URL, name it exactly `yourusername.github.io` (that gives you `https://yourusername.github.io/` with no subfolder).

3. **Upload the files.** Easiest path: on the new repo page, click "uploading an existing file" — then drag-and-drop `index.html`, `styles.css`, the entire `images/` folder, and this `README.md`. Commit.

   *Or, if you're comfortable with Git:*
   ```bash
   cd hani-portfolio
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/YOURUSERNAME/REPO.git
   git push -u origin main
   ```

4. **Enable Pages.** In the repo, go to **Settings → Pages**. Under "Build and deployment," set:
   - Source: **Deploy from a branch**
   - Branch: **main** / **/ (root)**

   Click Save. Wait a minute, then refresh. It'll show a URL like `https://yourusername.github.io/portfolio/`.

5. **Done.** Every time you push changes to `main`, the site updates automatically in ~30 seconds.

### Custom domain (optional)
If you own `hanialkarrain.com` (or similar), you can point it at GitHub Pages:
- Settings → Pages → Custom domain → enter your domain.
- At your domain registrar, add a CNAME record pointing to `yourusername.github.io`.
- GitHub handles HTTPS automatically after a few minutes.

---

## Things to consider adding later

- Real screenshots for all 15 games (biggest visual upgrade you can make)
- A favicon (`favicon.ico` in root) — search "favicon generator" for a quick tool
- Social embeds: a Spotify playlist embed, an itch.io widget, a YouTube iframe for the animated short — any of these can replace an image slot
- Analytics: drop in Plausible, Fathom, or GoatCounter if you care (Google Analytics works too)
- The arcade racer card currently has `href="#"` — update it once the game has a public link

---

Built in the style of a personal quarterly. Set in Fraunces and Georgia.
