# Soul Agri Command Centre

A single-page, Jarvis-style dashboard of Soul Agri / LNB business units: definitions, current state, competitors (India and Uganda), value chains, whiteboard path sketches, idea cards, plus a fertiliser market landscape page.

Everything is in `index.html` (HTML, CSS, JS and data inline). The only outside call is Google Fonts; if it is blocked, the page falls back to system fonts.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole site |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |
| `CNAME` | Add this yourself: one line with your domain (see below) |

## Deploy on GitHub Pages

1. Create a repository on GitHub (e.g. `soul-agri-command-centre`) and upload these files to the `main` branch.
   ```bash
   git init
   git add .
   git commit -m "Soul Agri Command Centre"
   git branch -M main
   git remote add origin https://github.com/<your-user>/soul-agri-command-centre.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
3. After a minute the site is live at `https://<your-user>.github.io/soul-agri-command-centre/`.

## Connect your own domain

Pick a subdomain, for example `command.yourdomain.com`.

1. In the repo add a file named `CNAME` containing only:
   ```
   command.yourdomain.com
   ```
   (Or type the domain in **Settings → Pages → Custom domain**, which creates the file for you.)
2. At your domain registrar / DNS provider add a record:
   - Subdomain: **CNAME** record, name `command`, value `<your-user>.github.io`
   - Root domain (`yourdomain.com`) instead: four **A** records pointing to
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
3. Wait for DNS to propagate (minutes to a few hours), then tick **Enforce HTTPS** in Settings → Pages.

## Privacy

GitHub Pages sites are public, even from a private repo on most plans. This page contains internal figures (acreage, budgets, processing economics, partner strategy). If it should stay internal, host it behind a login instead, for example:

- **Cloudflare Pages + Cloudflare Access** (free for small teams): restrict to your company emails.
- **Netlify** with password protection (paid plans).
- GitHub Enterprise Cloud with private Pages.

## Updating

Edit the data arrays near the top of the `<script>` in `index.html` (`V` for business units, `F` for the fertiliser page), commit and push. The site redeploys automatically.
