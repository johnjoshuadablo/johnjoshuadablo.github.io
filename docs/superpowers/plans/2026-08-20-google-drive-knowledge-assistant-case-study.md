# Google Drive Knowledge Assistant Case Study Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Publish a business-first Google Drive Knowledge Assistant case study with two sanitized workflow screenshots and an embedded TikTok demonstration while preserving a balanced six-card homepage grid.

**Architecture:** Add one static HTML case-study page using the shared `case-study.css`, copy the supplied screenshots into a dedicated public asset directory, and replace the homepage's Automated Website Blogs card with the new project. Add a responsive TikTok iframe component to the shared stylesheet, backed by a direct external link.

**Tech Stack:** Static HTML5, shared CSS, Python validation script, GitHub Pages, TikTok player iframe.

## Global Constraints

- Public title: `Google Drive Knowledge Assistant`.
- Public status: `Working prototype`.
- Do not claim a client deployment, measured ROI, reduced support volume, or production reliability.
- Keep AI Sales Copilot as the featured case study.
- Homepage must retain exactly six `study-card` entries.
- Rotate Automated Website Blogs off the homepage only; do not delete `case-study-auto-website-blogs.html`.
- TikTok video ID: `7674636268759764231`; no autoplay; include a direct fallback link.
- Public screenshots must be copies of the supplied source files and preserve their aspect ratios.
- Do not stage or revert `images/case-studies/.DS_Store`.
- Publish through `master` and verify `https://joshuadablo.com` after GitHub Pages succeeds.

---

### Task 1: Add a Failing Static-Site Validator

**Files:**
- Create: `/tmp/validate_knowledge_assistant_case.py`
- Test: `/tmp/validate_knowledge_assistant_case.py`

**Interfaces:**
- Consumes: repository path `/Users/pcworth/Desktop/repos/freelance/johnjoshuadablo.github.io`.
- Produces: process exit code 0 only when the page, homepage card, assets, TikTok references, privacy wording, and six-card constraint are satisfied.

- [ ] **Step 1: Write the failing validator**

```python
from pathlib import Path
import re

repo = Path('/Users/pcworth/Desktop/repos/freelance/johnjoshuadablo.github.io')
index = (repo / 'index.html').read_text(encoding='utf-8')
page_path = repo / 'case-study-google-drive-knowledge-assistant.html'
assert page_path.exists(), 'new case-study page is missing'
page = page_path.read_text(encoding='utf-8')

assert 'case-study-google-drive-knowledge-assistant.html' in index
assert len(re.findall(r'class="study-card"', index)) == 6
assert 'Automated Website Blogs' not in index
assert (repo / 'case-study-auto-website-blogs.html').exists()
assert 'Google Drive Knowledge Assistant' in page
assert 'Working prototype' in page
assert '7674636268759764231' in page
assert 'https://www.tiktok.com/@josh.ai.automation/video/7674636268759764231' in page

assets = repo / 'images/case-studies/google-drive-knowledge-assistant'
for name in ('01-document-ingestion-workflow.png', '02-question-answering-workflow.png'):
    assert (assets / name).exists(), f'missing public asset: {name}'
    assert f'images/case-studies/google-drive-knowledge-assistant/{name}' in page

for forbidden in ('FW7iYPfMXmGpAIAb', 'pcworth-ai-replier-v2', 'apex-3072', 'api key', 'customer identity'):
    assert forbidden.lower() not in page.lower(), f'forbidden public detail: {forbidden}'

for unsupported in ('reduced support volume by', 'saved hours per week', 'production deployment'):
    assert unsupported.lower() not in page.lower(), f'unsupported claim: {unsupported}'

print('knowledge assistant portfolio validation: PASS')
```

- [ ] **Step 2: Run the validator and confirm the expected failure**

Run:

```bash
python3.11 /tmp/validate_knowledge_assistant_case.py
```

Expected: FAIL with `AssertionError: new case-study page is missing`.

---

### Task 2: Add Public Assets, Homepage Card, Case Page, and TikTok Styling

**Files:**
- Create: `images/case-studies/google-drive-knowledge-assistant/01-document-ingestion-workflow.png`
- Create: `images/case-studies/google-drive-knowledge-assistant/02-question-answering-workflow.png`
- Create: `case-study-google-drive-knowledge-assistant.html`
- Modify: `index.html:1545-1559`
- Modify: `case-study.css:395-451,524-595`
- Test: `/tmp/validate_knowledge_assistant_case.py`

**Interfaces:**
- Consumes: two supplied PNG files and existing site design classes.
- Produces: a linked public case study, balanced homepage grid, responsive screenshot gallery, and responsive TikTok player.

- [ ] **Step 1: Copy screenshot assets without modifying the sources**

Run:

```bash
mkdir -p images/case-studies/google-drive-knowledge-assistant
cp '/Users/pcworth/Library/Application Support/Hermes/composer-images/composer_2026-08-19_19-32-04-840_be5677.png' \
  images/case-studies/google-drive-knowledge-assistant/01-document-ingestion-workflow.png
cp '/Users/pcworth/Library/Application Support/Hermes/composer-images/composer_2026-08-19_19-31-49-457_8bc5d8.png' \
  images/case-studies/google-drive-knowledge-assistant/02-question-answering-workflow.png
```

- [ ] **Step 2: Replace the Automated Website Blogs homepage card**

Replace the `case-study-auto-website-blogs.html` card with:

```html
<a class="study-card" href="case-study-google-drive-knowledge-assistant.html">
  <span class="study-card-top">
    <span class="study-tag">Internal knowledge</span>
    <span class="study-number">04</span>
  </span>
  <span>
    <h3>Google Drive Knowledge Assistant</h3>
    <p>Watch a shared Drive folder, prepare company documents for search, and answer employee questions from those files.</p>
  </span>
  <span class="study-card-bottom">
    <span class="study-outcome">Faster internal answers</span>
    <span class="study-link">View solution</span>
  </span>
</a>
```

- [ ] **Step 3: Add responsive TikTok player styling to `case-study.css`**

Add:

```css
.video-proof {
  display: grid;
  grid-template-columns: minmax(0, 0.7fr) minmax(280px, 0.3fr);
  gap: 40px;
  align-items: center;
  padding: clamp(28px, 5vw, 52px);
  border: 1px solid var(--line);
  border-radius: 8px;
  background: var(--white);
  box-shadow: var(--shadow);
}

.video-frame {
  width: min(100%, 360px);
  aspect-ratio: 9 / 16;
  justify-self: center;
  overflow: hidden;
  border: 1px solid var(--line);
  border-radius: 12px;
  background: #000;
}

.video-frame iframe {
  width: 100%;
  height: 100%;
  border: 0;
}

.video-proof-copy p {
  margin-top: 18px;
  color: var(--muted);
  font-size: 17px;
  line-height: 1.7;
}
```

Add `.video-proof` to the single-column responsive selector at `max-width: 940px`.

- [ ] **Step 4: Create the new case-study page**

Create a page using `case-study-ai-sales-copilot.html` as the structural pattern with these exact content sections:

- Hero: company documents are already available but answers are difficult to find.
- Metadata: `Use case / Internal knowledge`, `Source / Google Drive`, `Status / Working prototype`.
- Overview: employees ask the system questions; it searches uploaded policies and SOPs before answering.
- Problem cards: hard-to-find files, repeated questions, inconsistent answers, onboarding delay, stale documents, unsupported-answer risk.
- Solution: document-ingestion pipeline plus question-answering pipeline.
- Architecture nodes: `Shared Drive folder`, `Document preparation`, `Searchable knowledge`, `Employee question`, `Relevant sections`, `Grounded answer`, `Explicit fallback`.
- Working proof list: new/updated files detected, document sections indexed, matching sections retrieved, missing-answer fallback, two pipeline screenshots, public TikTok demonstration.
- Technologies: Google Drive, n8n, Google Gemini, Pinecone, document splitting, retrieval-based answering.
- Gallery: the two copied workflow screenshots with business-language captions.
- TikTok iframe:

```html
<iframe
  src="https://www.tiktok.com/player/v1/7674636268759764231?autoplay=0&loop=0&music_info=1&description=1"
  title="TikTok demonstration of the Google Drive Knowledge Assistant"
  loading="lazy"
  allow="fullscreen">
</iframe>
```

- Direct fallback link:

```html
<a class="button button-secondary"
  href="https://www.tiktok.com/@josh.ai.automation/video/7674636268759764231"
  target="_blank" rel="noopener">Watch on TikTok</a>
```

- [ ] **Step 5: Run the validator and require a pass**

Run:

```bash
python3.11 /tmp/validate_knowledge_assistant_case.py
```

Expected: `knowledge assistant portfolio validation: PASS`.

- [ ] **Step 6: Run static checks**

Run:

```bash
git diff --check
git status --short
git diff --stat
git diff -- index.html case-study.css case-study-google-drive-knowledge-assistant.html
```

Expected: no whitespace errors; only intended source files plus the known `.DS_Store` change and new assets are listed.

---

### Task 3: Perform Local Browser, Privacy, Link, and Console QA

**Files:**
- Verify: `index.html`
- Verify: `case-study-google-drive-knowledge-assistant.html`
- Verify: `case-study.css`
- Verify: `images/case-studies/google-drive-knowledge-assistant/*.png`

**Interfaces:**
- Consumes: completed static-site implementation.
- Produces: evidence that the case page is readable, private details are absent, images and links load, TikTok placement is usable, and JavaScript emits no console errors.

- [ ] **Step 1: Start a tracked local server**

Run:

```bash
python3.11 -m http.server 8765 --bind 127.0.0.1
```

Use a tracked background process, not `&` or `nohup`.

- [ ] **Step 2: Open the homepage and case study with cache-busting queries**

Open:

- `http://127.0.0.1:8765/?verify=knowledge-assistant`
- `http://127.0.0.1:8765/case-study-google-drive-knowledge-assistant.html?verify=knowledge-assistant`

- [ ] **Step 3: Inspect the homepage and full case page visually**

Verify:

- Six balanced homepage cards.
- New card appears in the former card 04 position.
- Hero, sections, screenshots, and TikTok block do not clip.
- Both screenshots remain legible on desktop and stack correctly at mobile width.
- TikTok player uses a narrow vertical frame and does not autoplay.

- [ ] **Step 4: Verify console and local assets**

Require zero uncaught JavaScript errors. Request these URLs and require HTTP 200:

```bash
curl -I http://127.0.0.1:8765/case-study-google-drive-knowledge-assistant.html
curl -I http://127.0.0.1:8765/images/case-studies/google-drive-knowledge-assistant/01-document-ingestion-workflow.png
curl -I http://127.0.0.1:8765/images/case-studies/google-drive-knowledge-assistant/02-question-answering-workflow.png
```

- [ ] **Step 5: Stop the local server**

Stop the tracked process and confirm it is no longer running.

---

### Task 4: Commit, Deploy, Verify Live, and Preserve Context

**Files:**
- Stage: `index.html`
- Stage: `case-study.css`
- Stage: `case-study-google-drive-knowledge-assistant.html`
- Stage: `images/case-studies/google-drive-knowledge-assistant/`
- Create/update: `~/Documents/Obsidian Vault/30_Sessions/2026-08-20_google-drive-knowledge-assistant-portfolio.md`
- Modify: `~/Documents/Obsidian Vault/30_Sessions/Index.md`

**Interfaces:**
- Consumes: verified local implementation.
- Produces: published GitHub Pages case study, synchronized repository, and retrievable session context.

- [ ] **Step 1: Stage only intended portfolio files**

Run:

```bash
git add index.html case-study.css case-study-google-drive-knowledge-assistant.html \
  images/case-studies/google-drive-knowledge-assistant/
git diff --cached --check
git status --short
git diff --cached --stat
```

Confirm `images/case-studies/.DS_Store` remains unstaged.

- [ ] **Step 2: Commit and push**

Run:

```bash
git commit -m "feat: add Google Drive knowledge assistant case study"
git push origin master
```

- [ ] **Step 3: Wait for GitHub Pages**

Run:

```bash
export HEAD_SHA=$(git rev-parse HEAD)
RUN_ID=$(gh run list --limit 20 --json databaseId,headSha,status,conclusion,workflowName,url \
  | python3.11 -c 'import json, os, sys; runs=json.load(sys.stdin); sha=os.environ["HEAD_SHA"]; print(next(str(r["databaseId"]) for r in runs if r["headSha"] == sha))')
test -n "$RUN_ID"
gh run watch "$RUN_ID" --exit-status
```

Expected: the command selects the run whose `headSha` equals the pushed commit and the watch exits with a successful conclusion.

- [ ] **Step 4: Verify the live custom domain**

Run:

```bash
HEAD_SHA=$(git rev-parse HEAD)
curl -sS -L --max-time 30 -o /tmp/live-portfolio.html -w 'HTTP %{http_code}\n' \
  "https://joshuadablo.com/?verify=${HEAD_SHA}"
curl -sS -L --max-time 30 -o /tmp/live-knowledge-assistant.html -w 'HTTP %{http_code}\n' \
  "https://joshuadablo.com/case-study-google-drive-knowledge-assistant.html?verify=${HEAD_SHA}"
python3.11 - <<'PY'
from pathlib import Path
index = Path('/tmp/live-portfolio.html').read_text(encoding='utf-8')
page = Path('/tmp/live-knowledge-assistant.html').read_text(encoding='utf-8')
assert 'Google Drive Knowledge Assistant' in index
assert 'Working prototype' in page
assert '7674636268759764231' in page
print('live custom-domain content: PASS')
PY
git fetch origin
git rev-list --left-right --count origin/master...master
```

Expected: both HTTP requests return 200, content check passes, and branch comparison returns `0 0`.

- [ ] **Step 5: Verify the live pages in the browser**

Open both cache-busted URLs and confirm the accessibility tree contains the new card, case-study headline, screenshot captions, TikTok section, and CTA.

- [ ] **Step 6: Update long-term session context**

Write an Obsidian recap containing the public URL, positioning, homepage-card rotation, screenshots used, TikTok placement, privacy decision, and verification evidence. Add it to `30_Sessions/Index.md`, seed the recap into Mnemosyne, and run two recall queries covering the homepage placement and TikTok proof.

- [ ] **Step 7: Run the spoken completion cue**

Run:

```bash
/Users/pcworth/.hermes/im_finish.sh
```
