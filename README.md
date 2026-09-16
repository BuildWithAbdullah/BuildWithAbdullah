# Abdullah Shabbir

**Web Solutions Engineer. Performance, Accessibility, SEO and Security.**

Slow website? Failed ADA audit? Hacked website? Poor Core Web Vitals? Need AI
features or automation? Those are the problems I work on.

Platform-agnostic. I fix root causes rather than symptoms, and I write
solutions that survive the next deployment and the next developer.

---

## What I do

**Accessibility** ADA, WCAG 2.0, 2.1 and 2.2 Level AA. Audits, remediation and
verification across themes, page builders and closed platforms, including PDF
and form remediation. Manual screen reader and keyboard testing, not scanner
output alone.

**Performance and Core Web Vitals** LCP, INP, CLS, FCP and TTFB. Diagnosis by
phase attribution, so the fix addresses the part of the metric that is actually
slow.

**Security and emergency recovery** Hardening, malware cleanup, blocklist
delisting, white screen of death recovery, and post-incident work that closes
the entry point rather than just removing the payload.

**Technical SEO** Crawlability, indexation, structured data, Search Console
diagnostics, redirects and migrations.

**AI integration and automation** OpenAI API integrations, chatbots, and
workflow automation built into real production systems.

Plus e-commerce build and maintenance: WooCommerce, Shopify and Liquid.

---

## Certifications

- **DHS Trusted Tester for Section 508 and WCAG**, January 2026
- **IAAP Web Accessibility Specialist (WAS)**, September 2025
- **IAAP Certified Professional in Accessibility Core Competencies (CPACC)**, April 2025

WAS and CPACC together form the IAAP CPWA credential. Trusted Tester is the
qualification for United States federal and state government accessibility
work.

---

## Tools

| Repository | What it is |
|---|---|
| [site-audit-cli](https://github.com/BuildWithAbdullah/site-audit-cli) | One command that audits a page for accessibility, Core Web Vitals, technical SEO and response-header security, and then reports the WCAG criteria no scanner can check. Self-contained HTML, Markdown and JSON reports, budgets and CI exit codes. 38 tests, including a fixture built correctly to prove the tool stays quiet when a page is right. |

## Pattern libraries

These are patterns, not client work. Everything here is generalised, runnable
and, where it can be, verified by machine. All of them are drawn from delivered
engagements except ai-integration-patterns, which is a capability repository and
says so in its own README.

| Repository | What it is |
|---|---|
| [wcag-fix-library](https://github.com/BuildWithAbdullah/wcag-fix-library) | Failing and corrected markup for 16 WCAG 2.2 criteria. An axe-core harness in CI asserts every corrected example is clean and every failing example still fails. Seven criteria are marked as not machine-detectable, with what a scanner reports on a page that plainly fails them. |
| [shopify-accessibility-patterns](https://github.com/BuildWithAbdullah/shopify-accessibility-patterns) | Liquid snippets, a CSS baseline and focus management for Online Store 2.0 themes, plus what cannot be fixed at theme level and how to report it. |
| [wix-squarespace-accessibility](https://github.com/BuildWithAbdullah/wix-squarespace-accessibility) | A tested injection layer for closed platforms: idempotent, non-destructive, observer-driven. And the argument for when not to use it. |
| [core-web-vitals-checklist](https://github.com/BuildWithAbdullah/core-web-vitals-checklist) | Diagnosis and fix order for LCP, INP and CLS, organised around phase attribution. Field measurement included. |
| [wordpress-security-hardening](https://github.com/BuildWithAbdullah/wordpress-security-hardening) | Hardening as must-use plugins, a live header verification script, and the reasoning behind the decisions that are judgement rather than code. |
| [technical-seo-toolkit](https://github.com/BuildWithAbdullah/technical-seo-toolkit) | Crawlability, indexation, structured data and measurement patterns, each with a failing and a corrected artefact checked in CI. Six of the ten produce no Search Console report at all, which is the argument for the repository. |
| [ai-integration-patterns](https://github.com/BuildWithAbdullah/ai-integration-patterns) | Transport, streaming, structured output, a tool allowlist, the trust boundary and cost ceilings for a language model behind a website. 58 tests, no dependencies, no API key needed to run them. A capability repository rather than extracted client work, and it says so. |

---

## How I work

**Automated tools are the floor, not the ceiling.** Roughly a third of WCAG
success criteria are machine-testable, and the operability failures cluster in
the part that is not. A site can return zero violations and still have a
checkout drawer a keyboard user cannot escape. Every audit I do includes a
manual keyboard and screen reader pass.

**A passing score is not the goal, a usable site is.** Where a scanner flag is
a false positive, I document the reasoning instead of changing markup to
satisfy the tool. Silencing a warning in a way that breaks keyboard access is a
worse outcome than the warning.

**Overlays and auto-patch scripts do not work.** They can only repair what a
machine can detect, they interfere with the assistive technology people already
use, and they leave the underlying markup untouched. I remove them and fix the
source.

**I write down what I did not do, and why.** A decision not to deploy a
Content Security Policy, or not to force two-factor before administrators are
enrolled, is a finding with reasoning attached. An undocumented omission just
looks like an oversight.

---

## Stack

`WordPress` `WooCommerce` `Shopify` `Liquid` `Elementor` `Divi` `Wix`
`Squarespace` `React` `Next.js` `TypeScript` `JavaScript` `PHP` `HTML5` `CSS3`
`Tailwind` `REST APIs` `GA4` `GTM` `Klaviyo` `Zapier`

**Accessibility tooling** `axe DevTools` `WAVE` `Lighthouse` `NVDA` `PAC 3`

---

## Background

Based in Lahore, working with clients in the US, UK, EU and Australia.
