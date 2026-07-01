# Link Tree

A single-file, self-hosted replacement for Linktree. One `index.html`, no build
step, hosted free on Netlify.

## Edit your links

Open `index.html`. Everything you'll change is marked with `EDIT THESE` comment
blocks:

- **Title / share preview** — the `<title>` and `<meta>` tags in `<head>`.
- **Avatar** — either uncomment the `<img class="avatar">` line and drop an
  `avatar.jpg` next to `index.html`, or keep the monogram (`YN`) fallback.
- **Name + tagline** — the `<h1>` and `.tagline`.
- **Links** — each link is one `<a class="link">` block. Copy a block to add a
  link, delete a block to remove one. The emoji in `.icon` is optional.
- **Socials** — the compact text row at the bottom. Delete it if you don't want it.

Preview locally by just opening the file in a browser:

```
open index.html
```

## Deploy to Netlify

### Option A — drag & drop (fastest, no git)

1. Go to <https://app.netlify.com/drop>
2. Drag this folder onto the page.
3. Done — you get a live `something.netlify.app` URL.

To update later, drag the folder again (or connect git, below).

### Option B — git + auto-deploy (recommended)

1. Create a repo and push this folder:
   ```
   git init && git add . && git commit -m "Initial link tree"
   git remote add origin <your-repo-url>
   git push -u origin main
   ```
2. In Netlify: **Add new site → Import an existing project** → pick the repo.
3. Leave the build command blank; publish directory is `.` (already set in
   `netlify.toml`). Deploy.
4. Every future `git push` auto-deploys.

## Custom domain

In your Netlify site: **Domain settings → Add a domain**, e.g.
`links.yourdomain.com`. Netlify walks you through the DNS record and provisions
a free HTTPS certificate automatically.

## Optional: analytics

Linktree's click tracking can be replaced with a privacy-friendly, cookie-free
tag. Add one line before `</head>` in `index.html`:

- **GoatCounter** (free): `<script data-goatcounter="https://YOURCODE.goatcounter.com/count" async src="//gc.zgo.at/count.js"></script>`
- **Plausible** (paid, self-hostable): `<script defer data-domain="links.yourdomain.com" src="https://plausible.io/js/script.js"></script>`

Or enable **Netlify Analytics** (server-side, paid add-on) with no code change.
