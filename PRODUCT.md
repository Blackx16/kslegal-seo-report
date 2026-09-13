# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Primary users are SEO specialists, agency consultants, and technical growth leads who need to communicate website audit findings clearly to two distinct stakeholder groups:
- **Decision-Makers / Executives**: Need immediate clarity on overall site health, high-level business risks, prioritized impact, and the business rationale for remediation.
- **Engineering & Implementation Teams**: Need precise, reproducible technical diagnostics, exact code fixes, and category-level deep dives (security headers, Schema.org JSON-LD, Core Web Vitals, robots/crawler directives, internal link equity).

## Product Purpose

Deliver a self-contained, interactive HTML audit report and executive dashboard that bridges the gap between deep technical diagnostics and high-stakes client presentations. Success means a client executive instantly grasps their site's health score and critical risks, while engineers can immediately copy validated fixes and structured data without proprietary software, third-party logins, or broken external dependencies.

## Positioning

Unlike bloated, static multi-page PDF exports from enterprise SEO SaaS tools (Ahrefs, Semrush) or bare developer CLI outputs (Lighthouse), this product compiles multi-dimensional SEO intelligence (technical, on-page, security, AI search/GEO, structured data, performance) into a single, zero-dependency, interactive HTML file that opens instantly anywhere, operates completely offline, and conveys high-craft agency authority.

## Operating Context

- Viewed in modern desktop and mobile web browsers directly from disk (`file://`), attached to client email deliverables, or hosted on static client preview links.
- Evaluated during client pitches, quarterly business reviews (QBRs), and technical handoff meetings with development agencies.
- Operates self-contained with no external backend servers, analytics tracking scripts, or authentication walls.

## Capabilities and Constraints

- **Single-File Portability**: All HTML, CSS, SVG icons, and JavaScript logic must be self-contained in a single deliverable for seamless sharing and offline durability.
- **Multi-Dimensional Categorical Breakdown**: Visualizes 14+ audit dimensions (Security Headers, Robots/Crawlability, Core Web Vitals, On-Page SEO, Entity/Schema, Broken/Internal Links, Readability, AI Search/GEO readiness).
- **Interactive Triage**: Severity-based filtering (`critical`, `warning`, `info`), category tab switching, light/dark mode toggling, and copyable code snippets.
- **Template & Python Generator Pipeline**: Populated dynamically via `.agents/scripts/generate_report.py`, generating outputs from live CLI audit passes and JSON data fixtures.

## Evidence on Hand

- Reference HTML implementation: [`seo-report-kslegal.html`](file:///Users/jasraj/dev/companyseo/seo-report-kslegal.html) (KS Legal & Associates interactive audit report).
- Generator engine: [`.agents/scripts/generate_report.py`](file:///Users/jasraj/dev/companyseo/.agents/scripts/generate_report.py).
- Structured audit payload: [`audit-kslegal.json`](file:///Users/jasraj/dev/companyseo/audit-kslegal.json).
- Supporting audit artifacts: [`KSLEGAL-FULL-AUDIT-REPORT.md`](file:///Users/jasraj/dev/companyseo/KSLEGAL-FULL-AUDIT-REPORT.md), [`KSLEGAL-ACTION-PLAN.md`](file:///Users/jasraj/dev/companyseo/KSLEGAL-ACTION-PLAN.md), [`KSLEGAL-LEGALSERVICE-SCHEMA.json`](file:///Users/jasraj/dev/companyseo/KSLEGAL-LEGALSERVICE-SCHEMA.json).

## Product Principles

1. **Dual-Lens Clarity**: Serve both the C-suite and the developer; lead with executive impact and health scores, backed by raw technical precision and copy-paste remediation.
2. **Zero-Friction Distribution**: The report must run anywhere, anytime—no external assets, no CDN failures, no login required, works completely offline.
3. **Actionable Over Exhaustive**: Every reported issue must provide a clear "why it matters" and a concrete, copy-paste fix rather than generic advice.
4. **Authoritative Craft**: The report represents the agency or consultant's brand; the interface must feel bespoke, polished, responsive, and data-dense without visual clutter.

## Accessibility & Inclusion

- Responsive from mobile viewports (375px) to ultrawide displays.
- WCAG AA compliant contrast ratios across both light and dark modes.
- Keyboard accessible tab navigation, clear focus states, and screen-reader accessible status badges (never relying solely on color to communicate severity).
