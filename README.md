# matthewshaffer.online — Migration Plan

## Intent

Take full control of my personal website (matthewshaffer.online). Move away from the
managed Bluehost/WordPress stack to a simple static site in a local Git repo, deployed
via GitHub Pages. This gives me direct control over the HTML/CSS, lets AI coding tools
work on the site seamlessly, and eliminates unnecessary hosting fees.

---

## Current Setup (audited 2026-02-19)

### Bluehost Account
- **Account number:** 53666090
- **Account owner:** Matthew Shaffer
- **Account email:** matthewshaffery10@gmail.com
- **Payment on file:** Visa ending 5106, expires 02/2026 (this month — needs attention before October renewal)

### Domain: matthewshaffer.online
- **Registrar:** Bluehost (confirmed — "Request Auth Code" available in dashboard)
- **Status:** Active
- **Expiration date:** Fri Oct 30, 2026
- **Auto-renew:** ON
- **Domain lock:** ON (must be turned off before any transfer)
- **Domain Privacy + Protection:** ON (provided by Perfect Privacy, LLC)
- **Registrant organization:** "Harvard Business School" (artifact from original registration while a PhD student; purely cosmetic, does not affect ownership or control)
- **Registrant email:** matthewshaffery10@gmail.com
- **Registrant phone:** 5188130492
- **Registrant address:** 19613 Vision Dr, Topanga, CA 90290-3116

### Products & Services (all auto-renew 10/30/2026 unless noted)
| Product | Notes |
|---|---|
| Web Hosting Package | WordPress Basic Hosting. 1 of 10 sites used. **This is what we're replacing.** |
| Domain Name (matthewshaffer.online) | The actual domain registration. **Must keep or transfer.** |
| Private Registration (matthewshaffer.online) | WHOIS privacy. Useful but free at Cloudflare Registrar. |
| CodeGuard Basic | Automated backup service. Unnecessary for a static site. |
| SiteLock Lite | Security scanning. "Expires 12/31/9999." Unnecessary for a static site. |

### Current WordPress Site
- **WordPress version:** 6.9.1
- **Installed plugins:** All in One SEO, MonsterInsights, OptinMonster, WPForms
- **Site URL:** https://matthewshaffer.online
- **Admin dashboard:** accessible via Bluehost > Websites > WordPress Admin

---

## What We Determined

1. **Bluehost is both host and registrar.** No hidden third-party registrar. The domain
   and hosting are bundled but can be separated.

2. **Everything renews 10/30/2026.** ~8 months from now. No urgency, but the Visa on
   file expires this month (02/2026). If it lapses and isn't updated, the October
   auto-renewal will fail. The domain must not be allowed to lapse accidentally.

3. **Five products, only one needed.** Of the five line items, only the domain
   registration itself matters going forward. The hosting, backups, security scanning,
   and paid WHOIS privacy are all unnecessary once we move to a static site with a
   registrar like Cloudflare (which includes free WHOIS privacy).

4. **The "Harvard Business School" owner field is cosmetic.** The account email, payment,
   and full dashboard access are all under matthewshaffery10@gmail.com. This can be
   updated in the Contacts tab or will be corrected during domain transfer.

5. **Domain transfer is straightforward when ready.** Dashboard has a "Request Auth Code"
   button under Domains > Move & Access. Turn off domain lock, get the auth code,
   initiate transfer at the new registrar (e.g., Cloudflare). Takes a few days.

---

## Plan

### Phase 1: Build the new site locally
- Create a simple, minimalist static site (HTML/CSS) that approximates the current look
- Keep it in this Git repo
- This can be done with any coding agent (Claude Code, Cowork, etc.)

### Phase 2: Deploy via GitHub Pages
- Push this repo to GitHub
- Enable GitHub Pages (Settings > Pages > deploy from branch)
- Site will be live at `<username>.github.io/<repo-name>` for testing

### Phase 3: Point the domain
- Option A (quick, no transfer): Update DNS records in Bluehost to point
  matthewshaffer.online at GitHub Pages. This gets the site live on the new platform
  immediately without transferring the domain yet.
- Option B (full migration): Transfer domain to Cloudflare Registrar, then configure
  DNS there to point at GitHub Pages.
- Either way, GitHub Pages supports custom domains with free HTTPS via Let's Encrypt.

### Phase 4: Cancel Bluehost
- Once the domain is transferred (or DNS is pointed away and you're ready to transfer),
  cancel all Bluehost products before 10/30/2026 renewal.
- Make sure the domain is safely transferred first so it doesn't lapse.

### GitHub Pages + Custom Domain: What's Needed
- A GitHub account (your existing one is fine; email doesn't need to match the domain)
- A repo containing the site files (index.html, etc.)
- In the repo's Settings > Pages, configure the custom domain: `matthewshaffer.online`
- At your DNS provider (Bluehost initially, Cloudflare later), create:
  - An `A` record pointing to GitHub Pages IPs (185.199.108-111.153)
  - A `CNAME` record for `www` pointing to `<username>.github.io`
- GitHub will auto-provision an HTTPS certificate once DNS propagates

---

## Audit Trail

All source documentation is in the `bluehost_audit/` subfolder:

| File | What it shows |
|---|---|
| `Screenshot 2026-02-19 at 11.47.36 AM.png` | Bluehost home dashboard — 1 domain, 1 website, account overview |
| `Screenshot 2026-02-19 at 11.47.50 AM.png` | Websites tab — WordPress Basic Hosting, site URL |
| `Screenshot 2026-02-19 at 11.48.09 AM.png` | Domain overview — status, owner, expiration (Oct 30 2026), auto-renew, domain lock |
| `Screenshot 2026-02-19 at 11.48.27 AM.png` | Domain contacts — registrant details, privacy protection provider |
| `Screenshot 2026-02-19 at 11.48.42 AM.png` | Move & Access tab — transfer options, "Request Auth Code" button |
| `Screenshot 2026-02-19 at 11.54.44 AM.png` | Accounts & Users — account number, user roles, email |
| `Screenshot 2026-02-19 at 11.55.00 AM.png` | Account details — payment info (Visa 5106, exp 02/2026), all 5 products/services with renewal dates |
| `Screenshot 2026-02-19 at 11.55.50 AM.png` | WordPress admin dashboard — WP 6.9.1, installed plugins |
| `02_Bluehost_Web_Hosting_October28_2025.pdf` | Most recent Bluehost bill (Oct 28, 2025) |
| `chat.txt` | Original chat conversation establishing context and plan |
