# Wen_Xuan106 — Site Admin

A separate, single-file website that lets you edit **wenxuan106-production-fansite.vercel.app** without touching code or GitHub's interface directly. It reads and writes straight to your `Wen_Xuan106-Production` GitHub repo through GitHub's API — save a change here, and the live site redeploys automatically (since Vercel is already connected to that repo).

## One-time setup: get a GitHub token

This admin page needs permission to write to your repo on your behalf. You do this once by creating a **Personal Access Token**:

1. Go to [github.com/settings/personal-access-tokens/new](https://github.com/settings/personal-access-tokens/new) (sign in if asked).
2. Under **Repository access**, choose **Only select repositories** → pick `Wen_Xuan106-Production`.
3. Under **Permissions → Repository permissions**, find **Contents** and set it to **Read and write**.
4. Click **Generate token** at the bottom.
5. **Copy the token immediately** — GitHub only shows it once. It'll look like `github_pat_11ABC...`.

Keep this token somewhere safe (like a password manager) — you'll paste it into the admin page each time you want to make an edit. It's never saved by the admin page itself; closing or refreshing the tab clears it, so you'll paste it in again next time.

## How to use the admin page

1. Open the admin page (see deployment below).
2. Paste your token into the **Personal Access Token** field.
3. Click **Load current site content** — it pulls in whatever's currently live.
4. Edit your tagline, bio, stats, links, lightstick colors, or upload a new photo.
5. Click **Save changes to GitHub**.
6. Wait about a minute — Vercel picks up the new commit and redeploys your site automatically.

## How to deploy this admin page

This is its own separate site from your fan site, so it needs its own repo and its own Vercel project:

1. Create a **new** GitHub repo (e.g. `wenxuan106-admin`) — this should be **private** if you don't want the admin URL discoverable by others, though the token itself is what actually protects write access.
2. Upload the `admin.html` file to that new repo, but **rename it to `index.html`** when uploading (so Vercel serves it at the root URL automatically).
3. Go to [vercel.com](https://vercel.com), sign in with GitHub, click **Add New… → Project**, import the `wenxuan106-admin` repo, and deploy with default settings.
4. You'll get a URL like `https://wenxuan106-admin.vercel.app` — bookmark it. That's your private editing panel.

## Notes

- Only give this token the **one repo** it needs (`Wen_Xuan106-Production`) with just **Contents: Read and write** — nothing else. That way, even if the token were ever exposed, the blast radius is limited to that one repo.
- Tokens can be revoked any time from [github.com/settings/personal-access-tokens](https://github.com/settings/personal-access-tokens) if you ever want to invalidate one.
- Treat the admin page's URL like a private link — anyone with the token *and* the URL could edit your site, though without the token, loading the page does nothing.
