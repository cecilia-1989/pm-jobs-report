# PM Jobs Report — Web App

Live site: **[data.jamesgunaca.com](https://data.jamesgunaca.com)**

## What this is
Interactive 31-slide viewer for the monthly PM Job Market Report, hosted via GitHub Pages and served at `data.jamesgunaca.com`.

Charts and data pull live from James's Google Sheets. Updated monthly by Cecilia via Claude.

## Monthly update process
1. James runs his Python script → Google Sheet updates
2. Cecilia opens the Claude project and types the monthly trigger command
3. Claude reads both Google Sheets, regenerates `index.html` with fresh data, and pushes to this repo
4. GitHub Pages auto-deploys within ~2 minutes
5. `data.jamesgunaca.com` is live with the new month's data

## Repo structure
```
index.html          ← The 31-slide interactive viewer (generated monthly by Claude)
CNAME               ← Points GitHub Pages to data.jamesgunaca.com
.github/workflows/  ← Auto-deploy on every push to main
README.md           ← This file
```

## First-time DNS setup (Squarespace)
In Squarespace DNS settings, add a CNAME record:
- **Host**: `data`
- **Value**: `cecilia-1989.github.io`
- **TTL**: Automatic

Then in this repo: Settings → Pages → Source: GitHub Actions → Custom domain: `data.jamesgunaca.com`
