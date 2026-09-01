# Personalized Opportunity Brief Pages — Design

## Goal

Create reusable, unlisted opportunity-brief pages on joshuadablo.com from Markdown files, starting with a personalized Medicomm PPD production-cycle brief.

## Approved Approach

Use GitHub Pages' built-in Jekyll processing. Each brief is a Markdown file with front matter selecting one shared layout. No database, dashboard, JavaScript framework, authentication, or new runtime dependency.

## Page Structure

- Joshua Dablo branding and home link
- `Opportunity Brief` label
- Personalized recipient, title, summary, prepared-by information, and date from front matter
- Markdown body containing hypothesis, possible workflow, pilot design, suggested pilot targets, safeguards, and next-step question
- One CTA linking to Joshua's existing discovery-call calendar
- Footer with Joshua's email

## Privacy and Positioning

- Pages are not linked from the public homepage or navigation.
- Every opportunity page includes `noindex, noarchive` metadata.
- Unlisted does not mean private; content must contain no confidential information.
- Assumptions are labeled as hypotheses.
- Pilot metrics are suggested thresholds, not promised results.
- Editorial judgment and approval remain with Medicomm.

## URL

`https://joshuadablo.com/ideas/medicomm-ppd-production/`

The URL omits the prospect's personal name so the link can be forwarded internally without feeling individually addressed or exposing the outreach target.

## Files

- `_layouts/opportunity.html` — shared page shell and metadata
- `opportunity.css` — shared responsive presentation
- `ideas/medicomm-ppd-production.md` — personalized content and front matter

## Validation

A temporary validator must fail before implementation and pass afterward. Local Jekyll output must contain the expected title, recipient, noindex metadata, CTA, and suggested-target language. Browser QA must confirm readable desktop and mobile layouts, no overflow, and zero JavaScript console errors. Publication requires a successful GitHub Pages run and HTTP 200 from the custom-domain URL.
