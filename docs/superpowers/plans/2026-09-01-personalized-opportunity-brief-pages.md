# Personalized Opportunity Brief Pages Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Publish reusable Markdown-backed opportunity briefs on joshuadablo.com, beginning with Medicomm's PPD production-cycle idea.

**Architecture:** GitHub Pages processes each Markdown file through one Jekyll layout. One stylesheet handles all opportunity pages; front matter supplies personalization and metadata.

**Tech Stack:** GitHub Pages, Jekyll, Liquid, Markdown, HTML, CSS

## Global Constraints

- No database, admin dashboard, client authentication, JavaScript framework, or new production dependency.
- Opportunity pages stay absent from public homepage navigation and include `noindex, noarchive`.
- Treat Medicomm workflow details as hypotheses and metrics as suggested pilot targets.
- Keep editorial review and approval human-controlled.

---

### Task 1: Reusable Opportunity Page and First Brief

**Files:**
- Create: `_layouts/opportunity.html`
- Create: `opportunity.css`
- Create: `ideas/medicomm-ppd-production.md`
- Test: `/tmp/validate-opportunity-page.py`

**Interfaces:**
- Consumes: Markdown front matter fields `title`, `description`, `recipient`, `prepared_by`, `prepared_date`, `cta_url`, and `cta_label`.
- Produces: `/ideas/medicomm-ppd-production/` through `layout: opportunity` and `permalink`.

- [ ] **Step 1: Write failing validation**

Create a Python checker that requires all three source files, expected front matter, hypothesis language, suggested pilot-target language, safety review boundary, and absence of public homepage linking.

- [ ] **Step 2: Verify RED**

Run `python3.11 /tmp/validate-opportunity-page.py`. Expected: failure because `_layouts/opportunity.html` does not exist.

- [ ] **Step 3: Write minimal implementation**

Create shared Liquid layout, responsive CSS, and Medicomm Markdown brief using the approved copy from `/Users/pcworth/Downloads/medicommppdproductionnote.md`.

- [ ] **Step 4: Verify GREEN and build**

Run validator, then build with the available local Jekyll runtime. Inspect generated HTML for title, recipient, robots metadata, CTA, and rendered Markdown structure.

- [ ] **Step 5: Browser QA**

Serve generated output locally. Verify desktop and mobile presentation, internal links, zero horizontal overflow, and zero console errors.

- [ ] **Step 6: Publish and verify**

Stage only intended paths, commit, push `master`, wait for GitHub Pages, then verify HTTP 200 and expected unique content at the custom-domain URL.
