# Wen_Xuan106 — official site

A single-file website (`index.html`) — no build tools, no dependencies to install.

## Easiest way to edit it: editor.html

Open `editor.html` in your browser (just double-click it) — it's a simple form-based tool, pre-filled with your current content:

- Change your tagline, bio, stats, streaming/social links, or lightstick colors
- Upload a new photo (it gets embedded directly into the file, no separate image needed)
- Click **Download updated index.html** at the bottom — it downloads a ready-to-use `index.html` with your changes baked in
- Replace the old `index.html` in your GitHub repo with the new one and commit — that's it

`editor.html` itself never needs to go live; keep it on your computer and reopen it any time you want to make a change.

## How to edit it by hand (optional)

Open `index.html` in any text editor (Notepad, VS Code, TextEdit, etc.):

- **Text on the page** (hero title, tagline, bio) — look for `<!-- EDIT: ... -->` comments and change the words right after them.
- **Songs** — no editing needed. The Tracklist section embeds your live Spotify artist page, so new releases show up automatically whenever you drop them.
- **Streaming/social links** — scroll to the `SITE CONFIG` section near the bottom of the file (inside the `<script>` tag) and edit the `platforms` array. Add or remove a `{ ... }` block for each link.
- **Your photo** — replace the placeholder box in the "About" section with an `<img>` tag, as noted in the comment above it.
- **Colors** — the `:root { ... }` block near the top of the `<style>` section has named color variables (`--pink`, `--cyan`, etc.) you can change.

No coding experience needed — you're just editing words and links inside quotes.

## How to put it on the internet with GitHub (GitHub Pages)

1. Go to [github.com](https://github.com) and sign in (or create a free account).
2. Click the **+** icon top-right → **New repository**. Name it anything, e.g. `wenxuan106-site`. Make it **Public**. Click **Create repository**.
3. On the new repo page, click **uploading an existing file**.
4. Drag in `index.html` **and the `assets` folder** (it contains your photo) and click **Commit changes**.
5. Go to the repo's **Settings** tab → **Pages** (left sidebar).
6. Under **Build and deployment → Source**, choose **Deploy from a branch**. Under **Branch**, choose `main` and folder `/ (root)`, then **Save**.
7. Wait about a minute, then refresh the Pages settings screen — it will show your live URL, something like:
   `https://your-username.github.io/wenxuan106-site/`

That's it — every time you edit `index.html` in GitHub (or upload a new version) and commit, the live site updates automatically within a minute or two.

## How to put it on the internet with Vercel

This is a plain static site, so Vercel needs no build step or config file — it just serves `index.html` as-is.

**Option A — straight from GitHub (recommended, auto-updates on every commit):**
1. Push the site to a GitHub repo (see the GitHub Pages steps above if you haven't already).
2. Go to [vercel.com](https://vercel.com) and sign in with your GitHub account (free tier is fine).
3. Click **Add New… → Project**, then select your `wenxuan106-site` repo and click **Import**.
4. Leave all settings as default (Framework Preset: **Other**) and click **Deploy**.
5. After a minute, Vercel gives you a live URL like `https://wenxuan106-site.vercel.app`.
6. From then on, every commit you push to GitHub redeploys the site automatically.

**Option B — upload without GitHub:**
1. Go to [vercel.com](https://vercel.com) and sign in (any account works).
2. Click **Add New… → Project → Deploy without Git**, or drag the whole site folder (`index.html` + `assets` folder) onto the Vercel dashboard's upload area.
3. Click **Deploy**. You'll get the same kind of `.vercel.app` link.
4. To update later, re-upload the folder from the project's dashboard (this option doesn't auto-update — Option A does).

## Making edits later

- **Easiest**: edit the file directly on GitHub — open `index.html` in your repo, click the pencil icon, make changes, click **Commit changes**.
- **Locally**: download the file, edit it in a text editor, then re-upload it to GitHub (or use `git` if you're comfortable with it).
