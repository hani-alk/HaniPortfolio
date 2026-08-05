# Hani AlKarrain — Portfolio

Personal portfolio site. Static HTML + CSS, no build step, no dependencies, no JavaScript.

## Structure

```
HaniPortfolio/
├── index.html            ← landing page: "I'm a" + the four roles
├── music.html            ← Musician
├── games.html            ← Game developer (projects + awards)
├── athlete.html          ← Athlete (volleyball)
├── record-holder.html    ← Record holder (speedcubing)
├── styles.css            ← all styling, shared by every page
├── images/
└── README.md
```

Fonts (Fraunces + Amiri) load from Google Fonts. Everything else is local.

---

## How the landing page works

`index.html` is a two-column grid: the four role links on the left, a single preview
frame on the right. The frame holds all four images stacked on top of each other, and
CSS `:has()` fades in whichever one matches the role you're hovering:

```css
.hero:has(.role[data-role="music"]:hover) .stage img[data-role="music"] { opacity: 1 }
```

With nothing hovered, the music image sits at 22% opacity so the frame isn't empty.

Below 900px there's no hover, so the frame is hidden and each role instead shows a
small square thumbnail inline (`.role-thumb`). That's why each image appears twice in
the markup — same `src`, so the browser only downloads it once.

**To add or rename a role:** add an `<a class="role" data-role="X">` block, a matching
`<img data-role="X">` inside `.stage`, and add the two `X` selectors to the `:has()`
rule in `styles.css`.

---

## Working on it locally

Just open `index.html` in a browser — there's no server requirement. For auto-reload
on save, use the **Live Server** VS Code extension (right-click `index.html` → Open
with Live Server).

---

## Images

Referenced directly by filename from `images/`. All are cropped with `object-fit:
cover`, so the focal point matters more than exact dimensions — where a crop needs
help, there's an inline `style="object-position: center 35%"` on that specific `<img>`.

Compress with [tinypng.com](https://tinypng.com/) before committing; aim for under
~300KB each. `images/vb-naji.PNG` (~366KB) is currently the heaviest thing on the
landing page and is the best candidate if you want it faster.

`original images (ignored)/` is gitignored — it's the uncompressed source pile.

---

## Editing text

Copy lives in the page it belongs to. Nothing is shared or templated, so changing the
nav or footer means editing all five files.

---

## Deploying to GitHub Pages

1. Push to a public repo. For the cleanest URL, name it exactly `yourusername.github.io`.
2. Repo → **Settings → Pages** → Source: **Deploy from a branch**, Branch: **main** / **/ (root)**.
3. Every push to `main` redeploys in ~30 seconds.

### Custom domain
- Settings → Pages → Custom domain → enter your domain.
- At your registrar, add a CNAME record pointing to `yourusername.github.io`.
- GitHub provisions HTTPS automatically after a few minutes.

---

## Possible next steps

- Awad Racing on `games.html` is a non-linking card — turn it back into an `<a>` once there's a public link.
- Real screenshots for the remaining jam games are still the biggest visual upgrade available.
- Social embeds (Spotify player, itch.io widget) could replace an image slot on the relevant page.
