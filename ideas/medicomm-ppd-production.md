---
layout: opportunity
permalink: /ideas/medicomm-ppd-production/
title: Automating the PPD Production Cycle
description: A practical idea for testing whether mechanical preparation work can be reduced while keeping editorial judgment and approval fully human-controlled.
recipient: Medicomm Pacific, Inc.
prepared_by: Joshua Dablo
prepared_date: September 2026
cta_url: https://cal.com/joshua-dablo-vmto3x/free-automation-discovery-call
cta_label: Discuss the idea
---

## The opportunity to investigate

This note starts with a hypothesis, not a claim about Medicomm's confirmed internal process: preparing each PPD edition may involve substantial manual work to read product inserts, capture details, compare them with the previous edition, and prepare the content for editorial review and layout.

If that is broadly accurate, there may be three areas worth measuring:

- **Cost.** How much production time is spent on manual data entry and cross-checking rather than clinical or editorial judgment?
- **Speed.** Does the time required to prepare entries force an earlier content cut-off or delay production?
- **Capacity.** Could reducing mechanical preparation work free staff for custom publications, CPD programmes, client work, or other higher-value activities?

These assumptions need to be checked with the people who operate the process. The idea is to test whether the mechanical portion can be reduced while leaving editorial judgment and approval exactly where they are today.

---

## What could change

Subject to testing on Medicomm's actual source material, inserts — including scanned ones — could be processed automatically, with each product's details captured into a structured draft: name, brand, strength, form, dosing, contraindications, warnings, packaging, and manufacturer. The system could also identify possible duplicates, inconsistent terminology, new products, withdrawals, and changes from the previous edition for an editor to verify.

**What wouldn't change is the editorial responsibility.** No clinical judgment would be delegated to the system, and nothing would be published without editorial review and approval. If the approach works, editors would start from a prepared draft with possible changes already flagged instead of identifying every detail manually from the source documents.

---

## How to validate the idea

Nobody knows the real size of the saving until it is measured on actual inserts — which is testable without committing to a full implementation.

Take one representative drug class. Antihypertensives may be a suitable candidate, subject to Medicomm's recommendation: large enough to be meaningful, but bounded enough to test quickly. Before changing anything, establish how the work is currently done — time per product entry, where the time goes, and what kinds of corrections are normally required. Then process the same class through a small pilot and have an editor review the output using the normal workflow. Compare the two.

A few weeks, one class, and the result should be clear enough to support a decision.

---

## Suggested pilot targets

The figures below are proposed thresholds for discussion, not promised results. The final targets should be agreed with Medicomm before testing and measured against the current-process baseline.

### Staff-hours per product entry

A suggested target of at least 40% lower than the current baseline.

### Accuracy of captured details

A suggested threshold of 95% field-level accuracy or better, checked against an editor-verified sample. Field-level accuracy means the percentage of required product fields captured correctly when compared with the source insert and the editor-verified record.

### Changes correctly flagged

Every safety-relevant change in the agreed test set must be identified before the pilot can be considered viable.

### The editor's own verdict

The reviewer confirms that the output is genuinely usable as a starting draft in the existing editorial workflow.

---

## If the pilot doesn't clear the agreed bar

Then the sensible answer is to leave the process alone, and I would say so plainly. A reference that introduces errors is worse than one that is slow to produce — that trade is not worth making at any saving.

One likely constraint is source quality. If a large share of inserts are poor-quality scans, the exception rate could consume the expected gain. A bounded pilot would expose that early and make the limitation cheap to quantify.

---

## What it could open up

If product information eventually becomes clean, reusable records rather than content tied only to finished pages, the same reviewed information could support the print edition, digital platforms, and custom publications without being rebuilt each time.

That is a later opportunity. It only matters if the first pilot proves that the preparation workflow is accurate, useful, and worth continuing.

---

## Technical starting point

This idea was prompted by the open-source [Scientific Agent Skills](https://github.com/K-Dense-AI/scientific-agent-skills) project and its collection of scientific, medical, document-processing, and evidence-focused workflows. The repository is not a finished Medicomm solution; it is a useful technical reference for exploring a tightly controlled pilot around Medicomm's actual documents and editorial standards.

---

Is this worth a conversation? I would be interested to hear whether the bottleneck sits where I think it does — Medicomm's team would know far better where the hours actually go.
