# matthewshaffer.online — Site Specification for Recreation

This document describes the current site's structure and content so that a coding agent
(e.g., Claude Code) can recreate it as a simple static HTML/CSS site without needing
browser access to the live WordPress version.

The goal is a **minimalist, clean academic personal website** — simple enough to be
antifragile and fully under version control. No WordPress, no CMS, no build tools.
Just HTML and CSS files in a Git repo, deployed via GitHub Pages.

---

## Site Architecture

The current WordPress site has these pages (all linked from a persistent top nav):

```
matthewshaffer.online/
├── Home (/)                          ← landing page, bio blurb
├── Research (/research/)             ← list of papers with links
├── Teaching (/introduction-to-financial-accounting-buad-280-usc/)
│                                     ← lecture-note book page
├── CV (/cv/)                         ← links/embeds a PDF of the CV
├── AI in University Education Interview (/ai-in-university-education-interview/)
│                                     ← blog-post-style page (Oct 2023)
└── [Blog/Uncategorized posts]        ← minimal; may not need to recreate
```

The nav bar across all pages has links to at least: **Home, Research, Teaching, CV**.
The blog post about AI in education may be linked from the homepage or a blog section.

---

## Page-by-Page Content

### 1. Homepage (/)

**Purpose:** Brief introduction. Who I am, what I do, how to reach me.

**Content:**

- **Name/title:** Matthew Shaffer
- **Position:** Associate Professor, UVA Darden School of Business
  (NOTE: he moved from USC Marshall to Darden in 2025 — make sure to use the current
  affiliation)
- **Research interests:** Empirical financial accounting, with particular interests in
  valuation, LLMs (large language models), and M&A
- **Contact email:** shafferm@darden.virginia.edu
- **Link to personal site:** matthewshaffer.online (implicit, since you're on it)
- **Photo:** There may be a headshot. Matt will need to provide this file locally if he
  wants one on the new site.

**Layout:** Very simple. Name prominently at top. A short paragraph bio. Contact info.
The WordPress theme appears to be a clean, minimal theme — light background, dark text,
no flashy design. Think academic simplicity.


### 2. Research (/research/)

**Purpose:** List of papers — working papers and publications.

**Content (papers known from search indexing and CV):**

#### Published / Accepted
- "Contentious Valuations: Accounting Reports as Schelling Points"
  — Available on SSRN. Has a video presentation link.
- Other publications in *Journal of Financial Economics*, *Management Science*,
  and *Review of Accounting Studies* (per Darden faculty profile)

#### Working Papers / Under Review
- "Scaling Core Earnings Measurement with Large Language Models" (with C. Wang)
  — Available on SSRN
- "Why Value the Enterprise en route to Equity? Valuation Practice in M&A" (with J. Lee)
- "Who Uses Corporate Sustainability Reports?" (with S. Burzillo and R. Sloan)
  — Also known as "Do Sustainability Reports Contain Financially Material Information?"
  — R&R at *Review of Accounting Studies*
- "Are Third-Party Fundamental Valuations Relevant in Public-Company Takeovers?"
- "Governance through Shame and Aspiration: Index Creation and Corporate Behavior"
  (with A. Chattopadhyay and C. [co-author])
- "Can Large Language Models Assess Merger Rationale?" (with J. Wegner)
  — Full draft being finalized for submission
- "Which Multiples Matter in M&A? An Overview"

**Layout:** Likely organized by section (Published, Working Papers) with paper titles,
co-authors, and links to PDFs or SSRN pages. Very standard academic research page.

**NOTE FOR REBUILD:** Matt will need to provide the actual SSRN URLs, PDF files, and
verify/update this paper list. The above is reconstructed from search indexing and the
November 2024 CV and will be somewhat out of date.


### 3. Teaching (/introduction-to-financial-accounting-buad-280-usc/)

**Purpose:** Information about a lecture-note textbook for Introduction to Financial
Accounting (BUAD 280, originally at USC).

**Content:**
- Description of the lecture-note book
- Possibly a link to download the PDF of the book
- The URL references USC's BUAD 280 course; Matt may want to update this for Darden

**Known hosted file:**
- `wp-content/uploads/2018/10/Introduction-to-Ratio-Analysis.pdf` — a teaching PDF

**NOTE FOR REBUILD:** Matt mentioned he'll need to drop the financial accounting text
locally so it can be included. The URL slug should probably be updated to something
institution-neutral (e.g., `/teaching/` or `/textbook/`).


### 4. CV (/cv/)

**Purpose:** Display or link to a downloadable PDF of the academic CV.

**Content:**
- Likely an embedded PDF viewer or a download link
- Most recent CV on the WordPress site:
  `wp-content/uploads/2024/11/mshaffer_cv_11_2024.pdf` (November 2024)

**NOTE FOR REBUILD:** Matt will need to drop the current CV PDF into the repo locally.
The static site can either link to it for download or embed it with an `<iframe>` or
`<object>` tag.


### 5. AI in University Education Interview (/ai-in-university-education-interview/)

**Purpose:** A blog-post-style page from October 2023 about AI in education.

**Content summary (from search indexing):**
- Published October 4, 2023
- Interview format discussing AI's role in university education
- Key themes: the tension between AI boosters and cynics; blending traditional pedagogy
  with AI tools; the continued importance of human judgment and mastery; his approach
  of being pro-AI for learning tools but old-school for exams; the potential for
  course-specific chatbots

**NOTE FOR REBUILD:** If Matt wants to keep this, the full text would need to be
exported from WordPress (or retyped/provided). It's a single blog post and can be a
standalone HTML page. Matt may or may not want to carry this forward — it could be
dropped or kept as a simple page.

---

## Design Notes

The current WordPress site uses a **minimal, clean theme** with:
- Light/white background
- Dark text (likely a serif or clean sans-serif font)
- Simple top navigation bar with page links
- No sidebar, no flashy widgets, no complex layout
- Very text-focused — this is an academic's personal site
- Footer is minimal (likely just a copyright or WordPress credit)

**For the static rebuild:** A single CSS file with clean typography should suffice.
Think: centered content column (~700-800px max-width), good font choices (e.g., system
fonts or a simple Google Font like Inter or Source Sans), clear heading hierarchy, and
links styled simply. No JavaScript needed for the basic site.

---

## Files Matt Needs to Provide Locally

These files are currently hosted on Bluehost/WordPress and need to be downloaded and
placed into the repo for the static site to be complete:

1. **CV PDF** — the current version of `mshaffer_cv_[date].pdf`
2. **Financial accounting textbook/lecture notes PDF** — the teaching material
3. **Headshot photo** (if one exists on the current site and he wants it on the new one)
4. **AI interview blog post text** — the full text, if he wants to keep this page
5. **Any other PDFs** linked from the research page (or these can just link to SSRN)

---

## Deployment Plan (GitHub Pages)

See README.md for the full migration plan. In brief:

1. Build the static site in this repo (HTML + CSS + asset files)
2. Push to GitHub
3. Enable GitHub Pages in repo Settings > Pages
4. Configure custom domain: `matthewshaffer.online`
5. At Bluehost (or after transferring to Cloudflare), set DNS:
   - `A` records → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - `CNAME` for `www` → `<github-username>.github.io`
6. GitHub auto-provisions HTTPS via Let's Encrypt

---

## Repo Structure (proposed)

```
personal_website/
├── index.html              ← homepage
├── research.html           ← research/papers page
├── teaching.html           ← teaching/textbook page
├── cv.html                 ← CV page (embeds or links PDF)
├── style.css               ← single stylesheet
├── assets/
│   ├── cv.pdf              ← current CV
│   ├── textbook.pdf        ← financial accounting lecture notes
│   ├── headshot.jpg         ← photo (if applicable)
│   └── [other PDFs]
├── CNAME                   ← contains "matthewshaffer.online" (for GitHub Pages)
├── README.md               ← project overview and migration plan
├── SITE_SPEC.md            ← this file
└── bluehost_audit/         ← archived screenshots, bill, and chat transcript
```
