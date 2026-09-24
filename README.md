# Supply Chain Security Readiness Assessment (prototype)

Interactive maturity assessment for software supply chain security, framed for the Mythos era. Twelve multiple-choice questions, four levels, and a report with a prioritized action plan. Built as a first-pass prototype for internal review and as the spec for a website lead-gen embed.

**Live prototype:** https://aditya-endor.github.io/supply-chain-readiness-assessment/

## How it works

| Piece | Detail |
|---|---|
| Questions | 12, three per dimension: Visibility, Prevention, Prioritization, Remediation & Governance. Each has three answers; only the top answer scores a point. |
| Levels | 0–3 Reactive · 4–6 Visible · 7–10 Prioritized · 11–12 Mythos-ready |
| Report | Level badge and description, 12-point scale, per-dimension meters, "what the next level does differently", an action plan ordered by impact with a tailored recommendation per missed question and the Endor Labs capability that addresses it, customer outcome stats, a why-now block, and a demo CTA. |
| Sharing | Answers are encoded in the URL hash (`#r=210120…`), so a result page is a shareable link. "Save report as PDF" uses a light print stylesheet. |
| Lead capture | The "Email me the report" form is a stub (`ETODO` in the script). HubSpot wiring and PDF generation are web-team items, as with the ROI calculator. |

Everything is one file, `index.html`, with CSS and JS scoped under `#endor-sscs` so it can be dropped into a Webflow embed. All copy lives in the `CONTENT` block at the top of the script (`DIMENSIONS`, `LEVELS`, `QUESTIONS`, `PRIORITY`). No build step.

## Sources the questions were built from

- FY27 message house: Software Supply Chain Security solution pillars (real-time enforcement at the registry edge, prioritize and fix what attackers can reach, harden the build pipeline) and the product frameworks for Package Firewall, SCA with Reachability, Container Reachability, SBOM Hub, Upgrade Impact Analysis, Endor Patches, Threat Center, AI Model Governance, CI/CD Security and Secrets Detection.
- Customer Solutions Onboarding Playbook (Confluence, Customer Solutions space). Its phase exit criteria are the CS team's working definition of value: reachability scans running → policies in warn mode, PR scans, Jira/Slack → block-merge policies, remediation strategy, automated remediation PRs, SBOM/VEX consumed, artifact signing. Questions 7, 10, 11 and 12 map directly to the Adopt and Action phases. "Time to first value" in that playbook is defined as noise reduction, first remediation and first blocked malicious package, which is why those three show up as the highest-priority gaps in the action plan.
- CS Health Score factors (Attributes, Engagement, Usage, ROI/Value, External Factors) informed the "Where you stand by dimension" and "What you already do well" sections, which give the prospect something concrete to bring to a first call.
- Jamie Scott's AppSec Maturity Staircase blog (Visibility → Workflows → Focus → Governance) shaped the four level definitions.
- "Implementing Software Supply Chain Security" whitepaper for the list of supply chain components (developers, code, dependencies, AI models, containers, CI/CD pipelines).
- Mythos talking points from the Claude Code Security competitive reference and the Library of Pain context.

## Stats used and their provenance

All figures are message-house proof points or cited third-party research: 92% fewer SCA findings, up to 90% container noise reduction, 6x faster CVE remediation, 83% fewer blocked PRs, 10x fewer security tickets, 150+ supply chain risk signals, 50 risk metrics per Hugging Face model, 40+ languages, 5M+ applications, exploits in hours for under $5 (Boston University), 90% of all OSV malware advisories ever filed came in 2025 (Endor Labs), ~40% of known malicious packages unavailable through public registries. Deliberately left out: the 94% breaking-change stat and the AURI token-efficiency study numbers.

## Before external use

1. Remove the "Prototype · internal review" badge in the header.
2. Confirm the customer name list (Atlassian, Cursor, Dropbox, Rubrik, Snowflake) is still approved.
3. Wire the email form to HubSpot and decide whether the report is gated or the PDF is the gate.
4. Add product deep links in the "How Endor Labs helps" blocks (left unlinked to avoid guessing slugs).
5. Get Customer Solutions feedback on the questions and the priority order (see the draft ask in the handoff notes).

## Local preview

```bash
open index.html
```
