# Auditing the Making (Frictional, Paper 1)

**An agent-run tool for evidence of how student work was made, tested on a synthetic benchmark.**

[Read the outline](paper1-outline.md) · [Help with the paper](CONTRIBUTING.md) · [Benchmark specification](synthetic-benchmark-spec.md)

**We're inviting collaborators.** Review one claim, check a source, or take on one of the tasks listed below. You don't need to review the whole paper to help. To join, follow [Getting started](CONTRIBUTING.md#getting-started) in the contributor guide.

## Abstract

*Working abstract. No manuscript exists yet, so this describes what the paper sets out to do. It reports no results.*

Generative AI can produce the artifacts that courses use as evidence of learning, so instructors need evidence of how a piece of work was made, not only of what it contains. This paper presents Frictional, a skill that a user's own AI agent runs locally against a folder or GitHub repository. It reports evidence about the artifact and about the process that produced it, and it gives findings, not scores or verdicts. We evaluate it on a synthetic benchmark of seeded issues, confound cases and manufactured process, with the expected findings frozen before any audit runs. We plan to report detection and false-positive rates for each dimension, whether confound cases receive the correct alternative explanations, consistency across repeated runs and model providers, and cost per repository. Synthetic evaluation establishes what the auditor can detect. It does not show that the patterns occur in real student work, or that the reports help instructors.

## Where the draft is

There is no draft yet. The closest document is the section-by-section outline, [paper1-outline.md](paper1-outline.md). The benchmark is specified in [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md).

## What needs to be done

- Settle the 12 open decisions at the end of the outline, including the title, the benchmark scale and the venue.
- Build the synthetic benchmark and freeze its expected findings.
- Run the auditor on the benchmark for each research question.
- Confirm the references still marked as unverified.
- Write the paper.

## How to contribute

Start with [Getting started](CONTRIBUTING.md#getting-started) in the [contributor guide](CONTRIBUTING.md): read the draft or plan, pick one thing to do, and email Nik to be added as a collaborator. The guide lists each kind of contribution with where to start and what to send, the rules for this repo, how to submit, and how credit and authorship work.

- **A quick contribution:** open an issue about one claim, source or decision. You don't need to review the whole paper.
- **To become an author:** take on a component of the work, help write the paper, approve the final version and agree to be accountable for it. The guide explains each step.

## Executive summary

**What this is:** the working repository for Paper 1 of the Frictional program. The working title is *Auditing the Making: An Agent-Run Tool for Evidence of How Student Work Was Made*. The paper evaluates the Frictional audit skill on a synthetic benchmark only, with no human subjects. The folder will be renamed to match the title you sign off on.

**Why read it:** this is Phase 1 of the outlining brief, delivered for sign-off. Nothing here is a draft of the paper, and no audit has been built or run.

**Where it stands (2026-11-22):**
- **Phase 0 (locate sources):** done; see [PROJECT.md](PROJECT.md). The preprint was found. No Frictional skill, dimension code or report template exists yet. stem-project-review is the template. Per your direction, the auditor does everything stem-project-review does, and adds the Frictional process dimensions wherever their evidence exists.
- **Phase 1 (outline):** done and awaiting your sign-off. The outline, the benchmark specification and the claims ledger are below; Paper 2's outline and IRB notes are in the sibling folder.
- **Phase 2 (drafting):** not started; out of scope until a later brief.

**Names:** the audit skill's repository will be `frictional`. The private Frictional book repository that held the name was renamed to `nikbearbrown/frictional-book` on 2026-11-22; the skill repository is [nikbearbrown/frictional](https://github.com/nikbearbrown/frictional). The papers are named by their titles: this folder for Paper 1, and `../process-evidence-in-practice` for Paper 2.

## Files

| File | What it is |
|---|---|
| [PROJECT.md](PROJECT.md) | Phase 0: the sources found and where; what carries over from stem-project-review; the dimension families |
| [paper1-outline.md](paper1-outline.md) | Paper 1 outline: titles, contribution, research questions, section claims and evidence, figures, metrics, threats, related work, venues, open decisions |
| [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md) | Every benchmark scenario, its variants, and the template for frozen expected findings |
| [claims-ledger.md](claims-ledger.md) | Every claim across **both** papers, with the evidence needed, its status and its source |
| [source/frictional-preprint.md](source/frictional-preprint.md) | The GLP preprint as published, in Markdown |
| [source/review-2026-11-22.md](source/review-2026-11-22.md) | The review of the preprint |
| [source/references-verified.md](source/references-verified.md) | References checked on 2026-11-22, including the trace of the BDNF figures |
| [source/agent-contrast-first-plan.md](source/agent-contrast-first-plan.md) | The first agent-contrast plan, superseded by the benchmark spec |

Paper 2 (the classroom study under IRB approval) is in `../process-evidence-in-practice/`. It holds [paper2-outline.md](../process-evidence-in-practice/paper2-outline.md) and [irb-protocol-notes.md](../process-evidence-in-practice/irb-protocol-notes.md).

## Rules this work follows

- No student data is opened, read or processed. Paper 1 uses synthetic data only.
- Nothing is invented. Unconfirmed references are marked UNVERIFIED or "verifying". Venue facts carry the date they were checked.
- You decide scope, venues, titles and claims. Each deliverable has blank sign-off fields for you.
- Never put student data in this repository.
