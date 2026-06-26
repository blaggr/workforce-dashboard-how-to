# Deploy guide — GitHub Pages (5 minutes, no command line)

## 1. Sign in to GitHub

If you don't have an account, create one at https://github.com/signup.

## 2. Create a new repository

- Click **+ → New repository** in the top right (or go to https://github.com/new).
- **Repository name:** `workforce-dashboard-how-to`
- **Visibility:** **Public** (required for GitHub Pages on the free tier)
- Leave all checkboxes unchecked. Click **Create repository**.

## 3. Upload the bundle files

On your new empty repo page, click the link **uploading an existing file**.

Drag these four files from this bundle:
- `index.html`
- `.nojekyll`
- `README.md`
- `DEPLOY.md`

If you can't see `.nojekyll` in Finder, press `Cmd + Shift + .` (period) to show hidden files. Alternatively, after uploading the visible three files, click **Add file → Create new file** in GitHub, name it exactly `.nojekyll`, leave content empty, and commit.

Scroll down, leave the commit message as default, click **Commit changes**.

## 4. Turn on GitHub Pages

- In the repo, click **Settings** (top right).
- In the left sidebar, click **Pages**.
- Under **Build and deployment → Source**, choose **Deploy from a branch**.
- Under **Branch**, choose **main** and **/ (root)**, click **Save**.

## 5. Get your URL

Wait 30–60 seconds. Refresh the Pages page. You'll see a green box with your live URL:

```
Your site is live at https://YOUR-USERNAME.github.io/workforce-dashboard-how-to/
```

Click it. Share it. Done.

## Updating the page later

When the report changes:
- In your repo, click on `index.html` → pencil icon → upload the new file → commit.
- Pages rebuilds within 60 seconds.

## Optional: custom domain

In Settings → Pages, add a custom domain (e.g., `report.example.org`). At your DNS provider, add a CNAME record pointing to `YOUR-USERNAME.github.io`. SSL is automatic.

## Optional: privacy-friendly analytics

To track views without using Google Analytics:
- **Plausible** — $9/month, no cookies. https://plausible.io
- **GoatCounter** — free for non-commercial. https://www.goatcounter.com/
- **Umami** — self-hosted free, or $9/month cloud. https://umami.is/

Add the provider's script tag inside the `<head>` of `index.html`, commit, redeploy.

## Alternative platforms

**Cloudflare Pages** — https://pages.cloudflare.com/ — drag-and-drop the `.zip`, no git required. URL pattern: `workforce-dashboard-how-to.pages.dev`. Faster CDN than GitHub Pages.

**Netlify** — https://app.netlify.com/drop — same drag-and-drop flow. URL pattern: `workforce-dashboard-how-to.netlify.app`.

GitHub Pages is recommended for academic/policy audiences because the `*.github.io/*` URL pattern reads as authoritative. Pick Cloudflare or Netlify if you want zero git and faster first-load matters more than URL signal.

## Troubleshooting

- **Page is blank after 60 seconds** — wait another minute, refresh. First build is slow.
- **Page shows `README.md` content instead of report** — `.nojekyll` did not upload. Add it directly in GitHub (Add file → Create new file → `.nojekyll` → empty → commit).
- **404 error** — make sure the URL ends with a trailing `/`. Without it, GitHub guesses wrong.
- **Page renders but tabs/filters/fonts broken** — `.nojekyll` is missing. See above.
- **"Settings → Pages" menu missing** — repo visibility must be Public for free-tier Pages.
