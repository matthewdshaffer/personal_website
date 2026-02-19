# Personal Website — matthewshaffer.online

## What this is

A static personal academic website for Matthew Shaffer, Associate Professor of Accounting at UVA Darden. Plain HTML + CSS, no build tools, no JavaScript, no frameworks. Deployed via GitHub Pages.

## File structure

```
index.html                              Home page (bio, contact)
research.html                           Papers — published + working
teaching.html                           Textbook download + courses
cv.html                                 Embedded PDF viewer + download
ai-in-university-education-interview/
  index.html                            Blog post (Oct 2023) — directory structure preserves original WordPress URL
style.css                               Single shared stylesheet
assets/
  ms_cv_2026_02_17.pdf                  Current CV
  shaffer_fin_accounting_text.pdf       Financial accounting textbook
CNAME                                   GitHub Pages custom domain config
```

## Conventions

- Every page shares the same header (name, title, affiliation) and nav bar. Keep these consistent across all pages.
- Nav links use relative paths (`index.html`, `research.html`, etc.). Subdirectory pages use `../` prefixes.
- The `active` class on a nav link marks the current page.
- CSS is a single flat file. No preprocessors, no CSS-in-JS.
- Paper list on research.html follows the CV's ordering and categorization (Peer-Reviewed Publications, then Working Papers).
- When updating the CV PDF, replace the file in `assets/` and update the filename reference in `cv.html`.

## Non-deployed files

These are in the repo for reference but are not part of the live site:

- `README.md` — Migration plan and Bluehost account audit
- `SITE_SPEC.md` — Original site content spec (used to build the initial static version)
- `bluehost_audit/` — Screenshots, billing PDF, and chat transcript from the Bluehost account audit
- `CLAUDE.md` — This file

## Deployment

GitHub Pages, custom domain `matthewshaffer.online`. The `CNAME` file tells GitHub Pages the domain. DNS must point to GitHub Pages IPs (see README.md for details).
