# Portfolio

Static personal portfolio site. Dark, monochrome, no build step.

## Run locally

Open `index.html` in a browser. That's it.

For a closer-to-prod experience (so relative paths and fonts work cleanly):

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Project structure

```
.
├── index.html              # homepage (single-scroll)
├── projects/
│   ├── project-one.html    # detail page templates
│   ├── project-two.html
│   └── project-three.html
├── assets/
│   ├── css/styles.css
│   ├── js/main.js
│   ├── img/                # placeholder SVGs — replace with real screenshots
│   └── resume.pdf          # TODO: add your real CV here
├── SPEC.md                 # design spec
└── README.md
```

## What needs filling in

Search the codebase for `TODO` — every placeholder is marked. The big ones:

- Name + hero tagline (`index.html`)
- About bio (3 paragraphs)
- Skills lists (languages, databases, tools)
- 4 experience entries (company, role, dates, bullets, tech)
- 3 projects: card on home + detail page + screenshot
- 4 "why hire me" claims
- 3 testimonials
- Contact email + GitHub handle
- `assets/resume.pdf`

## Deploying to GitHub Pages

1. Create a public repo on GitHub.
2. Push these files to `main`.
3. Repo → Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / root → Save.
4. Site goes live at `https://<your-username>.github.io/<repo-name>/`.

For a custom domain later, add a `CNAME` file with your domain and configure DNS.
