# FAYB Board

Static site for the **Fairhaven Acushnet Youth Baseball (FAYB)** board. Plain HTML and CSS. There is no build step and no framework.

The FAYB bot keeps the pages updated. This repository holds board content only. Do not commit passwords, API keys, or other secrets.

## Pages

| Path | Page |
| --- | --- |
| `/` | Home — welcome for board members and an upcoming-items placeholder |
| `/board/` | 2027 E-Board and support positions |
| `/minutes/` | November 4, 2026 meeting summary, with a link to the full Google Doc |
| `/calendar/` | Placeholder until calendar and event signup links are ready |

## Deploy on Netlify

A custom domain is optional. The default `*.netlify.app` address is enough.

1. Sign in at [Netlify](https://app.netlify.com).
2. Choose **Add new site** → **Import an existing project**.
3. Connect GitHub and select this repository (`FAYB-Board`).
4. Confirm the build settings. They are already set in `netlify.toml`:
   - **Build command:** leave empty (no build)
   - **Publish directory:** `.` (the site root)
5. Deploy.

Netlify serves `index.html` at `/`, and `board/index.html`, `minutes/index.html`, and `calendar/index.html` at `/board/`, `/minutes/`, and `/calendar/`. `404.html` is the not-found page.

`netlify.toml` also sets basic security headers. It does not contain secrets.

## Local preview

From the repository root:

```bash
python3 -m http.server 8080
```

Open [http://localhost:8080/](http://localhost:8080/).
