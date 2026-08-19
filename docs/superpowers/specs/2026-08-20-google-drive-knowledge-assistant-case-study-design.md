# Google Drive Knowledge Assistant Portfolio Case Study — Design

## Goal

Add a concise, credible case study to joshuadablo.com for Joshua's Google Drive document assistant prototype. The page should explain the business problem and working workflow in plain language, show the supplied n8n screenshots, and feature the published TikTok as a public demonstration.

## Positioning

Public title: **Google Drive Knowledge Assistant**

Core business outcome: company policies, SOPs, and reference files become easier for employees to search and use without repeatedly asking the same person.

Status claim: **Working prototype**. Do not claim a client deployment, measured ROI, reduced support volume, or production reliability.

## Homepage Placement

Keep the existing AI Sales Copilot as the featured case study.

Replace the homepage card for **Automated Website Blogs** with the new **Google Drive Knowledge Assistant** card. The Automated Website Blogs page remains published and directly accessible; only its homepage card is rotated out. This preserves the balanced six-card grid and gives homepage space to a more differentiated internal-knowledge automation example.

Homepage card:

- Tag: Internal knowledge
- Title: Google Drive Knowledge Assistant
- Description: Watches a shared Drive folder, prepares company documents for search, and answers employee questions from those files.
- Outcome: Faster internal answers
- Link: `case-study-google-drive-knowledge-assistant.html`

## Case-Study Structure

Follow the existing `case-study.css` visual system and current case-study page pattern.

1. **Hero**
   - Business-first headline and explanation.
   - Metadata: use case, intended team, and status (`Working prototype`).
2. **Overview**
   - Explain that the assistant turns existing company documents into a searchable internal reference.
3. **Business problem**
   - Policies and SOPs exist but are difficult to find.
   - Repeated questions depend on one knowledgeable person.
   - Different employees may give inconsistent answers.
4. **Solution**
   - A shared Google Drive folder remains the document source.
   - New and updated files are downloaded, split into searchable sections, and indexed.
   - Employees ask questions through chat; the system retrieves matching document sections before composing an answer.
5. **Safeguards and honest limitations**
   - Answers are grounded in the available files.
   - Missing information should produce an explicit unavailable-answer response rather than a fabricated policy.
   - Document quality controls answer quality.
   - The screenshots show a prototype architecture, not proof of production scale.
6. **Architecture**
   - Drive file change → document preparation → searchable knowledge store.
   - Employee question → relevant-document retrieval → answer.
7. **Working proof / gallery**
   - Supplied ingestion screenshot.
   - Supplied question-answering screenshot.
   - Captions explain each pipeline in business language before naming the tools.
8. **TikTok demo**
   - Responsive vertical embedded TikTok player for video ID `7674636268759764231`.
   - Direct `Watch on TikTok` fallback link.
   - No autoplay.
9. **Technologies**
   - Google Drive, n8n, Google Gemini, Pinecone, document chunking, retrieval-based answering.
10. **CTA**
    - Invite business owners to discuss repeated internal questions or hard-to-find operating documents.

## Images

Copy the supplied screenshots into:

`images/case-studies/google-drive-knowledge-assistant/`

Public filenames:

- `01-document-ingestion-workflow.png`
- `02-question-answering-workflow.png`

Privacy review found no visible client names, customer identities, credentials, API keys, workflow IDs, internal URLs, or private data. Preserve the original pixels and aspect ratios. Do not modify the source files.

## TikTok Embed

Use the official TikTok player iframe URL for the supplied video ID. Place it inside a responsive 9:16 container with a conservative maximum width so it remains readable on desktop and fits mobile screens. Include a direct external link as a fallback if TikTok blocks third-party playback.

## Validation

A temporary checker must fail before implementation and pass afterward. It will verify:

- New case-study page exists.
- Homepage links to the new page.
- Homepage still contains exactly six `study-card` entries.
- Automated Website Blogs is absent from the homepage grid but its HTML page still exists.
- Both public screenshots exist and are referenced with descriptive alt text.
- TikTok video ID and direct URL are present.
- `Working prototype` is present.
- Forbidden claims and private identifiers are absent.
- Internal image and page links resolve locally.

Browser QA must verify desktop and mobile layout, image legibility, TikTok placement, zero JavaScript console errors, and working navigation.

## Files Expected to Change

- `index.html`
- `case-study-google-drive-knowledge-assistant.html` (new)
- `case-study.css`
- `images/case-studies/google-drive-knowledge-assistant/01-document-ingestion-workflow.png` (new)
- `images/case-studies/google-drive-knowledge-assistant/02-question-answering-workflow.png` (new)
- This design document

Do not stage or revert `images/case-studies/.DS_Store`.

## Publication Standard

Completion requires a focused commit, successful push to `master`, successful GitHub Pages deployment, HTTP 200 from the cache-busted custom-domain URLs, expected unique text on the live page, and synchronized local/remote branches.