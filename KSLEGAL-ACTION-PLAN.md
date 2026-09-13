# SEO & Entity Strategic Action Plan: KS Legal & Associates

**Target Domain**: `https://www.kslegal.co.in/`  
**Execution Horizon**: 90 Days (Phase 1 to Phase 4)  
**Objective**: Elevate Organic Health Score from **46/100 to 85+/100**, eliminate critical technical debt, dominate high-intent Mumbai corporate/litigation queries, and capture AI search citations.

---

## Phase 1: Days 1–7 — Quick Wins & Technical Hygiene

### Action 1.1: Purge External URLs from XML Sitemap
* **Problem**: Third-party news links (*The Economic Times*, *YourStory*, *MoneyControl*) are listed in `sitemap.xml`.
* **Step-by-Step Implementation**:
  1. Log into WordPress Admin -> Go to **Rank Math** or **Yoast SEO** -> **Sitemap Settings**.
  2. Navigate to **Post Types** and inspect the custom post type for "Media Coverage" or "News".
  3. Toggle **"Include in Sitemap"** to **OFF** for any post type that uses external URL redirects.
  4. If custom rewrite rules were used, rebuild the sitemap cache.
  5. Go to **Google Search Console** -> **Sitemaps** -> Re-submit `https://www.kslegal.co.in/sitemap.xml`.
* **Expected Result**: 0 cross-host warnings in Search Console, 100% crawl budget focused on internal pages.

### Action 1.2: Deploy Security Headers in `.htaccess`
* **Problem**: Security headers scored 40/100; missing HSTS, X-Frame-Options, CSP, nosniff.
* **Implementation**: Add the following configuration block to the root `.htaccess` file on Hostinger:
  ```apache
  # KS Legal - Security Headers Configuration
  <IfModule mod_headers.c>
      # Enforce HTTPS for 1 year including subdomains
      Header always set Strict-Transport-Security "max-age=31536000; includeSubDomains; preload"
      # Prevent Clickjacking
      Header always set X-Frame-Options "SAMEORIGIN"
      # Prevent MIME-type Sniffing
      Header always set X-Content-Type-Options "nosniff"
      # Secure Referrer Information
      Header always set Referrer-Policy "strict-origin-when-cross-origin"
      # Restrict Browser Feature Access
      Header always set Permissions-Policy "camera=(), microphone=(), geolocation=()"
      # Upgrade Insecure Requests
      Header always set Content-Security-Policy "upgrade-insecure-requests"
  </IfModule>

  # Suppress PHP Version Fingerprinting
  <IfModule mod_headers.c>
      Header unset X-Powered-By
  </IfModule>
  ```
* **Expected Result**: Security score jumps from **40/100 to 95+/100**.

### Action 1.3: Immediate Metadata De-Spamming
* **Problem**: 2012-era repetitive keyword stuffing in homepage and practice page titles.
* **Updates**:
  * **Homepage**:
    * *Title*: `KS Legal & Associates | Corporate Law & Litigation Law Firm in Mumbai`
    * *Meta*: `KS Legal & Associates is a premier full-service Mumbai law firm specializing in corporate transactions, commercial litigation, NCLT insolvency, and arbitration.`
  * **Contact Page**:
    * *Title*: `Contact KS Legal & Associates | Law Offices in Nariman Point & BKC, Mumbai`
    * *Meta*: `Contact KS Legal & Associates at our Nariman Point and BKC Mumbai offices for confidential legal advisory in litigation, corporate law, and dispute resolution.`

### Action 1.4: Deploy `/llms.txt` for AI Search Engines
* **Implementation**: Upload the prepared file [`KSLEGAL-LLMS.txt`](file:///Users/jasraj/dev/companyseo/KSLEGAL-LLMS.txt) to the root directory of the web server as `/llms.txt`.
* **Verification**: Run `./.agents/scripts/agy-seo run llms_txt_checker.py https://www.kslegal.co.in/ --json` to verify HTTP 200 and 100% quality score.

---

## Phase 2: Weeks 2–4 — Entity Architecture & Local SEO

### Action 2.1: Implement Production `LegalService` Schema.org JSON-LD
* **Problem**: 0 `LegalService` schema nodes detected.
* **Implementation**:
  1. Open [`KSLEGAL-LEGALSERVICE-SCHEMA.json`](file:///Users/jasraj/dev/companyseo/KSLEGAL-LEGALSERVICE-SCHEMA.json).
  2. Embed this JSON-LD script inside the `<head>` of `header.php` (or inject via WordPress header script plugin):
     ```html
     <script type="application/ld+json">
     { ... contents of KSLEGAL-LEGALSERVICE-SCHEMA.json ... }
     </script>
     ```
  3. Validate using Google's Rich Results Test tool.

### Action 2.2: Google Business Profile (GBP) & Local Map Synchronization
* **Google Business Profile Audit**:
  * Verify official GBP listing name: `KS Legal & Associates`.
  * Set primary category: **Law firm**.
  * Add secondary categories: *Corporate law attorney*, *Legal services*, *Trial attorney*, *Real estate attorney*.
  * Add hours: Mon–Sat 9:30 AM – 7:30 PM.
  * Ensure address matches Nariman Point headquarters.
* **Website Map Embeds**:
  * On `/contact/` and `/about-ks-legal/`, embed responsive Google Maps iframes for both the **Nariman Point** and **Bandra Kurla Complex (BKC)** locations.

### Action 2.3: Internal Linking Overhaul
* **Step 1**: Replace all 16 occurrences of `"Read More"` anchor texts with keyword-focused phrases:
  * Replace `"Read More"` on the Banking snippet with `"Learn more about our Banking & Finance practice"`.
  * Replace `"Read More"` on Real Estate with `"View Real Estate & RERA legal services"`.
* **Step 2**: Rescue orphan article:
  * Link `https://www.kslegal.co.in/unilateral-appointment-of-arbitrator` from the main `/litigation-dispute-resolution/` practice page under an "Arbitration Precedents & Commentary" heading.

---

## Phase 3: Month 2 — YMYL Content Expansion & E-E-A-T Overhaul

### Action 3.1: Expand Thin Service Pages to Authority Guides (1,200+ Words)
Rewrite and expand the top 4 revenue practice pages:
1. **Corporate & Commercial Law** (`/corporate-commercial-laws/`):
   * Expand from 378 words to 1,200+ words.
   * Add H2 sections:
     * *Corporate Advisory & Regulatory Compliance in India*
     * *Cross-Border Mergers, Acquisitions & Joint Ventures*
     * *Commercial Contracts & Due Diligence Framework*
     * *Frequently Asked Questions on Indian Corporate Governance*
2. **Insolvency & Bankruptcy (NCLT/IBC)** (`/insolvency-bankruptcy/`):
   * Expand from 401 words to 1,400+ words.
   * Add H2 sections:
     * *Representation before NCLT Mumbai Benches & NCLAT New Delhi*
     * *Section 7 Petitions (Financial Creditors) vs Section 9 Petitions (Operational Creditors)*
     * *Defending Corporate Debtors in CIRP Proceedings*
     * *Key Timelines and Legal Thresholds under IBC 2016*
3. **Litigation & Dispute Resolution** (`/litigation-dispute-resolution/`):
   * Expand to include Bombay High Court original side litigation, domestic and international commercial arbitration, and section 9/11/34 Arbitration Act petitions.

### Action 3.2: Attorney Profiles & Author Authority
* Build an individual bio page for Managing Partner **Sonam Chandwani**:
  * Include high-resolution professional portrait.
  * Bar Council enrollment details, courts of practice, high-profile matters, academic credentials.
  * Links to national news articles where she is quoted as a legal expert (*Economic Times*, *YourStory*, *MoneyControl*).
  * Add `Person` Schema with `alumniOf`, `hasCredential`, and `sameAs` LinkedIn profile.

---

## Phase 4: Month 3 — Performance, AEO & Topical Clusters

### Action 4.1: Server Speed & LiteSpeed Optimization
* **Objective**: Reduce TTFB from 3,500ms+ to <400ms.
* **Actions**:
  1. Configure **LiteSpeed Cache (LSCache)** plugin on WordPress:
     * Enable Guest Mode & Guest Optimization.
     * Enable CSS/JS minification and HTTP/2 Push.
     * Configure cron-based cache crawler.
  2. Put **Cloudflare CDN** in front of Hostinger with Polish/Mirage and Indian Edge Nodes (Mumbai, Delhi, Chennai).

### Action 4.2: Answer Engine Optimization (AEO) Content Hubs
* Create structured legal FAQ hubs designed to capture Google Featured Snippets, People Also Ask (PAA), and Perplexity citations:
  * *Topic*: Indian Insolvency & Resolution Process
  * *Format*: Concise 50-word direct answers to core legal questions, followed by statutory breakdowns and table comparisons.

---

## Progress Milestone Tracking

| Milestone | Target Completion | Target Score | Success Indicator |
|-----------|-------------------|--------------|-------------------|
| **Phase 1** | Week 1 | **65 / 100** | Clean sitemap, 95/100 security headers, /llms.txt live, de-spammed titles |
| **Phase 2** | Week 4 | **75 / 100** | Schema.org 100% valid, GBP optimized, zero generic "Read More" links |
| **Phase 3** | Week 8 | **85 / 100** | Service pages expanded to 1,200+ words, E-E-A-T partner profiles indexed |
| **Phase 4** | Week 12 | **90+ / 100** | TTFB <400ms, first-page rankings for key commercial Mumbai legal queries |
