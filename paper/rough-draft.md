# Auditing the Making: Testing an Agent-Run Repository Audit on Synthetic Evidence

**Rough methods manuscript · November 27, 2026**

Protocol only. No benchmark performance, coverage estimate, or classroom outcome is reported.

## Abstract

A repository audit can report facts about the submitted artifact and about its visible development process. The same record may nonetheless support several explanations. We propose a synthetic benchmark to test whether Frictional reports evidence-backed observations, signals when evidence is unavailable, and avoids claims a snapshot cannot resolve. The design uses frozen expected findings, distinct observation and interpretation labels, and paired variants with different evidence availability. It measures detection, unsupported claims, abstention, repeatability, and resource use separately. The benchmark tests tool behavior on constructed cases; it cannot establish that a repository trace measures learning or that the report improves assessment.

## 1. Introduction

A tool can notice an incomplete README or a mismatch between a log and the repository it describes. Neither authorizes an inference about a person. A single visible commit shows the visible history of a specified branch, not the absence of offline work or earlier revisions. Frictional asks reviewers to judge the product and inspect available process evidence without converting observations into allegations or grades.

The primary research question is whether the tool recovers eligible facts frozen in advance while avoiding unsupported interpretations. Secondary questions concern evidence availability, attribution of alternative explanations, repeated-run stability and cost. [NIST's evaluation-probe project](https://www.nist.gov/programs-projects/building-evaluation-probes-agentic-ai) is a precedent for checking the fidelity, completeness and sufficiency of an agent's cited evidence. Here the object is a repository audit, not certification of a general verifier.

## 2. Tool and boundaries

The envisioned report ties each finding to a target snapshot, dimension, evidence pointer and status. It presents deterministic checks separately from interpretations and alternatives. Examples include whether a file exists, whether a referenced revision is visible and whether a reported result has a reproducible path. Evidence unavailable in the snapshot remains explicitly unavailable. No learning or authorship score is computed.

Use only constructed fictional materials. Treat files and logs as data, never instructions. The static path does not run target code; any planned dynamic reproduction test would use explicitly approved benign fixtures and an isolated environment without real credentials. Distinguish a blocked run from an observed reproduction failure.

## 3. Benchmark design

The [benchmark specification](../synthetic-benchmark-spec.md) proposes 25 scenario types across straightforward observations, plausible confounds, and stress cases. Its variants and run counts are planning options, not a collected dataset. Include genuine negative controls in each eligible dimension. Record authored, scripted, agent-built and hybrid construction as provenance, never as prediction labels.

[ASSUMPTION: the first release uses a feasible fixed subset, rather than every proposed variant.] Fix fixture selection, repository and template revisions, case-dependency groups, model and tool versions, scoring rules, and release plan before measurement. Keep related variants together in the holdout split; freeze and hash labels before the run, and withhold them from the auditor. If labels need correction, version and disclose the change.

Pair cases where an observation is warranted with cases where supporting evidence is unavailable. A squash-merge fixture is eligible for observations about the visible branch and for alternative explanations, not for a finding about the maker's effort. Preserve the ledger of blocked runs, schema failures, and retries under a fixed policy. Attribute stochastic variability to the full configuration unless the design isolates a single factor.

## 4. Analysis plan

| Measure | Denominator or unit | Meaning |
|---|---|---|
| Seeded-fact recall | Eligible expected facts; summarize by case and dimension | Whether observable test facts were found |
| Evidence-backed precision | Emitted factual findings judged | Whether reported facts have source support |
| Negative-control false flag rate | Eligible negative-control case–dimension pairs | Whether absent issues are reported |
| Evidence-state accuracy | Eligible cases with known unavailable, blocked or inapplicable states | Whether missing evidence is represented accurately |
| Interpretation overreach | Eligible reports in which the forbidden inference can be assessed | Whether the report claims more than its evidence |
| Repeatability and cost | Runs nested in fixture and configuration | Report agreement, latency and cost including retries |

**Table 1.** Proposed measures. Use fixed matching for deterministic findings and independently reviewed paraphrase rules for interpretations. Before unblinding model names, double-code ambiguous matches and report disagreement and adjudication. Document formally inapplicable checks; retain aborts and schema failures in flow counts. Cluster uncertainty by scenario family or use descriptive summaries if there are too few independent families. Report dimensions separately so easy checks do not hide difficult high-consequence failures.

## 5. Results (not yet collected)

[NEEDS: frozen case selection, run ledger, versioned reports and reviewed scoring outputs.] Present selected, attempted and scorable counts; then the measures in Table 1, paired evidence-availability contrasts, repeatability and cost. No example stands in for a held-out analysis.

## 6. Discussion

Synthetic fixtures give control over expected facts but may unintentionally favor checks developed by the same authors. Holdout independence, alternate authoring and transparent failure reporting address this threat without making a representativeness claim. Transfer to portfolios is a separate research question. [Process Evidence in Practice](https://github.com/nikbearbrown/process-evidence-in-practice) considers a later, approval-gated post-grade review. Neither is established by synthetic detection success.

## Data and ethics

No student work or participant data is involved in this proposal. Before claiming reproducibility, release a lawful synthetic fixture inventory, versions, expected labels, scoring code and scrubbed outputs. No benchmark run, submission, or external review occurred in this drafting pass.
