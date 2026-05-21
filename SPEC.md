# Portfolio Site — Spec

A personal portfolio site for an Outsystems / low-code developer. Dark, technical, monochrome aesthetic. Built static, hosted on GitHub Pages.

---

## 1. High-level decisions

| Decision | Choice |
|---|---|
| Aesthetic | Dark & technical, monochrome (white on near-black, gray for secondary) |
| Structure | **Hybrid** — single-page scroll for the overview, dedicated detail pages for individual projects |
| Primary goal | Personal brand / showcase (mixed audience: recruiters, peers, curious visitors) |
| Tech stack | Plain HTML / CSS / vanilla JS (no framework, no build step) |
| Hosting | GitHub Pages (free, static, easy custom domain later) |
| Animation level | Subtle — smooth scrolling, hover states, fade-in on scroll. No typewriter / parallax / heavy motion. |
| Content state | Placeholders throughout (clearly marked `TODO`) — owner fills in real content after scaffolding |

---

## 2. Visual design

### Color palette
- **Background:** `#0a0a0a` (near-black, not pure black — easier on the eyes)
- **Primary text:** `#ffffff`
- **Secondary text:** `#888888` (gray for metadata, dates, descriptions)
- **Borders / dividers:** `#1f1f1f` (subtle)
- **Hover / focus accent:** `#ffffff` underlines or border brightens; no color accent
- **No accent color** — strictly monochrome

### Typography
- **Body / UI:** `Inter` or system sans-serif fallback (`-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif`)
- **Headings:** same as body, heavier weight (600–700)
- **Monospace accents:** `JetBrains Mono`, `ui-monospace, SFMono-Regular, Menlo` — used sparingly for section labels, tech tags, code-like snippets
- All web fonts loaded from Google Fonts or self-hosted (decide at build time)

### Layout
- Max content width: **720–800px** centered (keeps it dense and readable)
- Generous vertical spacing between sections (96–128px)
- Single-column on mobile; project grid becomes 2-up on tablet, can stay 2-up on desktop

---

## 3. Site structure

### Home page (`/index.html`) — single long-scroll page

Sections in order:

1. **Hero**
2. **About**
3. **Skills & tech stack**
4. **Experience**
5. **Projects** (cards link to detail pages)
6. **Why hire me / characteristics**
7. **Testimonials**
8. **Contact** (also resume download lives here)

### Project detail pages (`/projects/<slug>.html`)
- One page per featured project (2–3 total)
- Linked from the homepage Project cards
- Each page: title, longer description, problem/solution, tech used, screenshots, links to GitHub repo + live demo (if any), "← Back to portfolio" link

---

## 4. Section-by-section detail

### 4.1 Hero
- Sticky top nav: `name` on left, anchor links on right (`About · Work · Projects · Contact`)
- Big name (h1)
- One-line tagline beneath (e.g. "Outsystems developer who ships pragmatic business apps") — **TODO**
- Two small links/buttons: `View work ↓` (scrolls to Projects), `Get in touch` (scrolls to Contact)
- No image, no animation beyond a soft fade-in on page load

### 4.2 About
- Section label: `// about` (monospace, gray)
- 2–3 paragraphs of bio — **TODO**
- Tone: first-person, conversational but professional

### 4.3 Skills & tech stack
- Section label: `// skills`
- Grouped lists (not a chart, no progress bars — those age badly):
  - **Primary:** Outsystems (Reactive Web Apps, Service Studio, Integration Studio)
  - **Languages:** TODO
  - **Databases:** TODO
  - **Other tools:** TODO
- Rendered as monospace text tags or simple comma-separated lists for a clean technical feel

### 4.4 Experience
- Section label: `// experience`
- **3–4 roles** displayed as a vertical list (most recent first)
- Each entry:
  - Company name + role title
  - Date range (right-aligned, gray, monospace)
  - 2–4 bullet points of accomplishments — **TODO**
  - Tech/tools used (small monospace tags)
- No company logos (keeps the monochrome aesthetic clean)

### 4.5 Projects
- Section label: `// projects`
- **2–3 featured projects** in a card grid (2-up on desktop)
- Each card contains:
  - Screenshot/thumbnail (16:9 ratio, placeholder image until real)
  - Project name
  - One-line description
  - Tech tags (monospace, small)
  - Links: `GitHub →` and `Read more →` (Read more goes to the detail page)
- Hover state: card border brightens, slight lift (subtle transform)

### 4.6 Why hire me / characteristics
- Section label: `// why hire me`
- 3–5 short claims, each with one line of supporting detail — **TODO**
- Example structure:
  - **Pragmatic.** I optimize for shipping, not for the cleverest abstraction.
  - **Translates business needs.** I'm comfortable with stakeholders, not just code.
  - **(more TODO)**
- Rendered as a clean list, not boxes/cards — keeps it understated

### 4.7 Testimonials
- Section label: `// testimonials`
- 2–3 short quotes — **TODO**
- Each: quote text, attribution (name, role, company), gray
- Plain text, no quote-mark graphics or photos

### 4.8 Contact
- Section label: `// contact`
- Short prompt: "Open to chat about Outsystems work, side projects, or anything in between."
- Two visible links:
  - **Email:** `mailto:` link — **TODO** (email)
  - **GitHub:** profile URL — **TODO** (handle)
- **Resume download** button: `Download CV (PDF) ↓` — links to `/assets/resume.pdf` (placeholder PDF until real one provided)
- No contact form (no backend needed for GitHub Pages)

### 4.9 Footer
- Centered, very small
- Year + name + `Built with HTML/CSS/JS` + GitHub repo link

---

## 5. Interaction & behavior

- Smooth-scroll on nav anchor clicks
- Fade-in-on-scroll for each section (IntersectionObserver, ~10 lines of JS)
- Sticky nav with subtle background blur when scrolled past hero
- Card hover: 150ms transition on border + transform
- All interactions degrade gracefully without JS (content is fully visible, just no fade-ins)

---

## 6. Accessibility & responsiveness

- Semantic HTML (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- Color contrast meets WCAG AA on the dark background
- Keyboard-navigable; visible focus rings
- Responsive breakpoints:
  - Mobile (<640px): single column, nav collapses to hamburger or wraps
  - Tablet (640–1024px): project grid becomes 2-up
  - Desktop (>1024px): max-width container centers the content
- All images have alt text
- Resume link clearly labeled with file type and size

---

## 7. File / folder structure

```
portfolio/
├── index.html
├── projects/
│   ├── project-one.html       (TODO: rename to real slug)
│   ├── project-two.html
│   └── project-three.html     (optional, only if 3 projects)
├── assets/
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   └── main.js
│   ├── img/
│   │   ├── project-one.png    (TODO placeholder screenshots)
│   │   ├── project-two.png
│   │   └── project-three.png
│   └── resume.pdf             (TODO: real PDF)
├── README.md
└── SPEC.md                    (this file)
```

---

## 8. Deployment

- Repo pushed to GitHub
- Settings → Pages → deploy from `main` branch, `/` root
- Site available at `https://<github-username>.github.io/<repo-name>/`
- Custom domain optional (can be added later via `CNAME` file)

---

## 9. Content TODO checklist

Things the owner needs to provide before launch:

- [ ] Full name
- [ ] Hero tagline (one line)
- [ ] About bio (2–3 paragraphs)
- [ ] Skill lists: languages, databases, other tools (Outsystems is the anchor)
- [ ] 3–4 prior roles: company, title, dates, 2–4 bullets each, tech used
- [ ] 2–3 featured projects: name, one-liner, longer description, tech, GitHub URL, live demo URL (if any), screenshot
- [ ] 3–5 "why hire me" claims with one-line support
- [ ] 2–3 testimonials with attribution
- [ ] Contact email
- [ ] GitHub handle
- [ ] Resume PDF

---

## 10. Out of scope (v1)

- Blog / writing section
- CMS or dynamic content (everything is hand-edited HTML)
- Contact form with backend
- Dynamic GitHub-repo fetching
- Analytics (can be added trivially later)
- Light mode toggle (site is dark-only by design)
- Custom domain (post-launch decision)
