# Abdullah Shabbir

**Web engineer. I handle the technical side of websites: speed, SEO,
accessibility, security, development and AI.**

Slow website? Failed ADA audit? Hacked website? Poor Core Web Vitals? Need AI
features or automation? Those are the problems I work on, and have since 2023.

Platform-agnostic. I fix root causes rather than symptoms, and I write
solutions that survive the next deployment and the next developer.

[workwithabdullah.dev](https://workwithabdullah.dev) &middot;
[Webwright Labs](https://webwrightlabs.com) &middot;
[hello@workwithabdullah.dev](mailto:hello@workwithabdullah.dev)

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

## Tools

| Repository | What it is |
|---|---|
| [site-audit-cli](https://github.com/BuildWithAbdullah/site-audit-cli) | One command that audits a page for accessibility, Core Web Vitals, technical SEO and response-header security, and then reports the WCAG criteria no scanner can check. Self-contained HTML, Markdown and JSON reports, budgets and CI exit codes. Every finding the tool can emit lives in one catalogue, and the suite drives 52 of its 53 entries out of real calls into the real modules and then asserts the two sets match in both directions, so the documentation cannot drift from the code. 50 tests and 351 repository assertions, including a fixture built correctly on purpose to prove the tool stays quiet when a page is right. CI runs Node 22 and 24, plus a job that installs on the exact minimum version so the supported range is tested rather than asserted. |
| [wordpress-emergency-recovery](https://github.com/BuildWithAbdullah/wordpress-emergency-recovery) | `wp-triage` reads a broken or compromised WordPress install from the filesystem and reports 58 findings across 11 check modules, each with file and line evidence, a next action, and a statement of what it does not prove. It never writes to the install, never opens a database connection and never makes a network request, and CI asserts all three rather than taking my word for it. Plus symptom to cause decision trees for the eight ways a site goes down, and the page on what to do in the first ten minutes, before anybody changes anything. |
| [site-migration-and-dns](https://github.com/BuildWithAbdullah/site-migration-and-dns) | `migrate-check` verifies a website migration before and after the switch: DNS zone shape, the TTL arithmetic that sets how long a rollback takes, SPF, DKIM and DMARC so mail survives a zone rebuilt at a new host, certificate coverage, redirect map coverage, mixed content, and the staging robots.txt and canonical that get shipped live. Plus a serialization aware search and replace for the byte length prefixes a plain text replace silently breaks. 74 findings, 213 tests, ten failing and corrected pairs, and a test asserting every catalogued finding is reachable. Only the collector touches the network, and CI asserts that too. |

## Pattern libraries

These are patterns, not client work. Everything here is generalised, runnable
and, where it can be, verified by machine. Most are drawn from delivered
engagements. ai-integration-patterns is a capability repository and says so in
its own README.

| Repository | What it is |
|---|---|
| [wcag-fix-library](https://github.com/BuildWithAbdullah/wcag-fix-library) | Failing and corrected markup for 16 WCAG 2.2 criteria at Levels A and AA. Nine of them a scanner reports and seven it does not, and the seven are the point: they are judged by code in the repository that drives a real browser, presses real keys and measures what is painted. That claim used to be a paragraph and is now an assertion checked in both directions on every run. axe-core, filtered to the conformance target, has to report zero violations on all seven failing pages, while the repository's own judging has to report failures on those same seven. If a scanner ever starts catching one of them the build goes red, which is correct, because the sentence saying it cannot has become false and has to be rewritten rather than left standing. The repository also records all four things a scanner can do with a defect, not only the one that reaches the number everybody quotes. The clearest case is the button whose aria-labelledby points at an id that does not exist: it has no accessible name at all, and axe examines it and reports neither a pass nor a violation, so a pipeline gating on the violation count sees a clean page. The rule actually named nested-interactive examines a button inside a link and passes it, measured by enabling that rule on its own so it is not an artefact of the tag filter. Writing the measurements found defects in the measurements. The obvious way to check focus visibility is to diff the indicator properties before and after focus, and written that way the page that carries outline:none on every element passes, because the browser moves outline-offset on :focus-visible whether or not there is an outline to offset. The judging now asks what puts ink on the screen. And an intersection is not an occlusion: the first version of the obscuring check failed a correct page, because a skip link at a higher stacking level geometrically overlaps the header it sits above. Everything under lib/ judges and has never seen a browser, and CI fails a judge that imports puppeteer or touches document, which is what makes 42 tests of the judging possible with no browser at all. 171 tests, 886 repository assertions, 72 catalogued findings, and 14 limits each observed on a corrected page and asserted there, so the section on what the repository does not check cannot quietly go out of date. Node 22 and 24, plus a job on the exact engines floor. |
| [accessible-react-components](https://github.com/BuildWithAbdullah/accessible-react-components) | Six ARIA Authoring Practices patterns in React and TypeScript: modal dialog, combobox, tabs, disclosure, menu button and toast region. Each ships twice, once as the version that usually arrives in a pull request and once corrected, and 33 behavioural audits mount both and press keys rather than reading markup. The suite requires every audit to fail on the failing version as well as pass on the corrected one, so no check in the repository is one that has never been seen to catch anything, and every audit states what it proves and what a headless DOM cannot show it. The toast pair is the one worth opening: it passes every static check, because the defect is when the live region appeared. 274 tests, 730 repository assertions, Node 18, 20 and 22. |
| [shopify-accessibility-patterns](https://github.com/BuildWithAbdullah/shopify-accessibility-patterns) | Liquid snippets, a CSS baseline and focus management for Online Store 2.0 themes, plus what cannot be fixed at theme level and how to report it. A catalogue of 32 findings, one per reason a check can fire rather than one per check, each with its fix and what it cannot establish, and every one observed firing in CI. Eleven failing and corrected pages reach 17 of those findings; eight fixtures reach the other 15, and writing them turned up nine defects in the detectors. Six declared limits are asserted rather than written down, four in both directions: for the cart drawer, all four combinations of the static verdict and the repository's own focus arithmetic are constructed, so neither is evidence for the other. 356 tests, 308 repository assertions, no dependencies. |
| [wix-squarespace-accessibility](https://github.com/BuildWithAbdullah/wix-squarespace-accessibility) | Eight accessibility repairs for Wix and Squarespace, where the markup cannot be edited at all. Each ships with the page as the platform emits it and the page as it should be, and the suite asks three things of every pair: that the failing page produces exactly the findings it claims, that the corrected page is clean, and that the injected layer earns the same grade as fixing the page at source would. Four of the fifteen catalogued findings cannot be detected by reading markup, which is why the suite drives a real browser. The clearest is the mobile overlay that never takes focus: the toggle has a role, a name and aria-expanded, the overlay has links, every attribute a scanner can read is correct, and a keyboard user still tabs through the whole page behind it. Writing the tests found seven defects that had already shipped. Five rules each decided whether a control was already named by reading textContent, so a button named by an image alt was given a second name and announced itself twice. The filename-alt rule cleared every filename alt, which on an image that is the only content of a link removed the link's entire name, so a repair installed for 1.1.1 created a 4.1.2 failure. And the mobile navigation rule watched the menu with a 250ms setInterval in a repository whose own documentation gives that exact thing as the failure its design prevents. One pair is there because the layer cannot fix it, and the finding it leaves behind is asserted on every run. 115 tests, 327 repository assertions, Node 22 and 24. |
| [core-web-vitals-checklist](https://github.com/BuildWithAbdullah/core-web-vitals-checklist) | Diagnosis and fix order for LCP, INP and CLS, organised around phase attribution rather than a list of tips. A catalogue of 37 findings across 34 rules, each filed under the metric and the phase it would move, and each carrying a sentence about what it does not prove. That sentence is the argument of the whole repository, so it is asserted rather than written down. For every finding that names a phase, the real arithmetic admits a breakdown where that phase does not dominate: same page, same finding, different visits, different next action. It asserts the converse too, that knowing which phase dominates narrows the cause to a set of candidate findings rather than to one, and the single phase where it narrows to exactly one is declared as an exception and checked as an exception. The eleven failing and corrected pairs declare the exact set of findings that survives each repair, both ways, because asserting that a repaired page is clean is easy and slightly dishonest when it is only clean under the rules written for it. Every corrected page in the repository still reports that it measures nothing. Ten further fixtures exist because the pairs only ever reach 15 of the 37 findings, and four of the eight defects found while building this were in rules the pairs never touch. The worst of them: space was treated as reserved by any declared height, so the unsized image example, whose own comment names width 100 percent and height auto as the reason the defect is so common, passed the check written to catch it. The block reader also read every at-rule as a style rule with the selector font-face, the font metric rule missed the idiomatic adjusted-fallback fix and reported the repository's own corrected page, listeners were paired to handler bodies by array index so a named callback made every later handler read the wrong body, and a refused sendBeacon was dropped in silence, which loses exactly the records from the slowest sessions, which are the ones the 75th percentile is made of. The collector reads documents and decides nothing; the rules decide everything and have never seen a document, and CI fails a rule file that reaches for raw text or a DOM. The browser entry point is now wiring only, with the rating, the arithmetic, the payload and the transport lifted into a module driven by stubs, and a check that fails the build if any of it moves back into the file no test can import. 127 tests and 171 repository assertions, identical on Node 20, 22 and 24, with the test count read from the structured event stream rather than from reporter output, because Node 24 prints the spec reporter where 20 and 22 print TAP. No dependencies, no network, no browser. |
| [wordpress-security-hardening](https://github.com/BuildWithAbdullah/wordpress-security-hardening) | Hardening as must-use plugins, plus the reasoning behind the decisions that are judgement rather than code. The plugins are loaded under a hook registry and their real hooks fired, so the header set, the removed XML-RPC methods and every branch of the login allowlist are asserted on without a WordPress install, a database or a network request. The header check is split in two and the half that decides anything makes no request at all, so all seventeen of its findings are driven out of saved responses rather than needing a site to point at. Writing the tests found six defects that had already shipped, including a plugin that sent its headers on the front end and not on the login page, which is the URL actually under attack, and an address allowlist built on ip2long that refused the login form to any administrator arriving over IPv6 while their other address sat in the list. 82 tests, 472 repository assertions, fourteen failing and corrected pairs, Node 20, 22 and 24. |
| [technical-seo-toolkit](https://github.com/BuildWithAbdullah/technical-seo-toolkit) | Crawlability, indexation, structured data and measurement patterns, each with a failing and a corrected artefact checked in CI. Six of the ten produce no Search Console report at all, which is the argument for the repository. Every finding the checkers can emit now lives in one catalogue, 62 of them, and the suite drives all 62 out of real calls into the real checkers and then asserts the two sets match in both directions. Writing those tests found six defects that had already shipped. The worst was the check for render assets blocked in robots.txt, which matched the asset list against robots.txt paths without taking the path out of the URL, so it reported nothing for the input a browser network panel actually gives you, which is to say it passed every site it existed to catch. Another validated the spelling of a sitemap lastmod rather than the date, and accepted 2026-02-30. A failing example that produces only the absence of a thing is now rejected as evidence, because a page with no h1 is a failing heading example and so is a blank document. 142 tests, 1161 repository assertions, Node 20, 22 and 24. |
| [ai-integration-patterns](https://github.com/BuildWithAbdullah/ai-integration-patterns) | Transport, streaming, structured output, a tool allowlist, the trust boundary and cost ceilings for a language model behind a website. Every module ships beside a naive implementation of the same thing, and ten pairs grade both: the naive side has to keep exhibiting exactly the defect it is there for, and the fixed side has to keep exhibiting exactly the limits the repository admits it cannot clear. Writing them found fifteen defects that had already shipped. The validator guarding the tool boundary used `key in value`, which walks the prototype chain, so a tool call carrying a property named constructor satisfied a schema that forbade additional properties. It also ignored every constraint it had not implemented, so minLength 8 accepted the empty string, and a typo in a type validated nothing at all. The budget ceiling checked, then awaited, then recorded, so three concurrent requests of 805 tokens all passed a ceiling of 1000. And the abort path, in a file whose own comment explains that an abandoned response keeps billing until somebody hangs up, only checked the signal when an event arrived, so a stream that had gone quiet could not be cancelled; the first attempt at fixing that reintroduced it, and the pair caught both. 158 tests, 487 repository assertions, 61 catalogued failure modes, no dependencies, no API key needed to run any of it. A capability repository rather than extracted client work, and it says so. |

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

## Webwright Labs

I run [Webwright Labs](https://webwrightlabs.com), a small web studio, and I
lead the engineering there. I work with a small team, and I work white label for
agencies, which means the work ships under your name and your client never hears
mine.

The repositories above are mine rather than the studio's. They are patterns
pulled out of delivered work and generalised until nothing client-specific is
left, which is why they can be published at all.

---

## Contact

| | |
|---|---|
| Hiring and contract work | [hello@workwithabdullah.dev](mailto:hello@workwithabdullah.dev) |
| Studio and agency work | [hello@webwrightlabs.com](mailto:hello@webwrightlabs.com) |
| Personal site | [workwithabdullah.dev](https://workwithabdullah.dev) |
| Studio | [webwrightlabs.com](https://webwrightlabs.com) |
| LinkedIn | [abdullah-shabbir-web-engineer](https://www.linkedin.com/in/abdullah-shabbir-web-engineer/) |

Remote, and fully flexible to your time zone wherever you are.
