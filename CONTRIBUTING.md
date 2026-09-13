# Contributing to KS Legal SEO & Diagnostic Workstation

Thank you for your interest in contributing to the KS Legal SEO Diagnostic Workstation and audit intelligence deliverables.

## How to Contribute

### Reporting Bugs or Regressions
If you discover an issue in the report calculations, UI telemetry display, or schema payloads:
1. Search existing [Issues](https://github.com/Blackx16/kslegal-seo-report/issues) to verify it has not already been reported.
2. Open a new issue using the [Bug Report Template](.github/ISSUE_TEMPLATE/bug_report.md).
3. Include reproduction steps, browser version, and relevant snippets from `audit-kslegal.json`.

### Suggesting Improvements or Features
1. Open a feature request via [Issues](https://github.com/Blackx16/kslegal-seo-report/issues).
2. Clearly explain the rationale, target SEO/GEO benefit, and impacted deliverables.

### Pull Requests
1. Fork the repository and create a descriptive feature branch:
   ```bash
   git checkout -b feature/seo-schema-enhancement
   ```
2. Make your modifications cleanly, maintaining formatting in Markdown, JSON, and HTML.
3. Test local rendering of `index.html` across both dark and light modes.
4. Commit your changes with conventional commit messages (`feat:`, `fix:`, `docs:`).
5. Push to your fork and submit a Pull Request against `main`.

## Code & Data Standards
- Maintain valid JSON-LD schemas verified against Schema.org specifications.
- Follow the visual tokens defined in [DESIGN.md](DESIGN.md).
- Adhere to the Product Contract outlined in [PRODUCT.md](PRODUCT.md).
