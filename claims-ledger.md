> **Provenance.** Drafted by Claude Code, model Claude Opus 5.5 (`claude-opus-5-5`), on 2026-11-22. Phase 1 deliverable covering both papers.
>
> **Human sign-off** (left blank until a human fills it in)
> Name: ____________ Date: ____________ Decision (approved / approved with changes / rejected): ____________ Notes: ____________

# Claims ledger: both Frictional papers

## Executive summary

**What this is:** every claim either paper would make, with the evidence it needs, its status, and where the claim or evidence comes from. It also lists the preprint's claims that are being cut, and why.

**Why read it:** a claim with no evidence behind it does not go in either paper. This ledger is the check. When a result comes in or a source is confirmed, its row changes status here first.

**What it shows:**
- 9 background claims, mostly **have**.
- 10 design claims, all **to collect**, because the skill does not exist yet.
- 9 Paper 1 result claims and 11 Paper 2 result claims, all **to collect**.
- 14 preprint claims reviewed:
  - 10 cut or moved to future work;
  - 2 to verify or soften;
  - 1 recast as Paper 2's secondary analysis;
  - 1 kept as a design stance.

The cut list includes two the review did not flag: the preprint's statement that a "labeled corpus" is already published (it is not), and the unsourced claim that AI audio is "spectrographically indistinguishable" from professional recordings.

Status values: **have** (evidence exists and is verified), **to collect** (the study must produce it), **to verify** (a source exists but has not been confirmed), **cut** (removed, with the reason).

## Background claims (both papers)

| ID | Claim | Paper | Evidence needed | Status | Source |
|---|---|---|---|---|---|
| L1 | Generative AI weakens the inference from a finished artifact to the process that produced it. | 1, 2 | The argument, plus evidence that artifacts can be produced without the process | have | Preprint §1–2; Weber-Wulff et al. 2023; Liang et al. 2023 |
| L2 | Output-only AI-text detectors are unreliable and can be biased against some writers. | 1, 2 | Empirical detector studies | have | Weber-Wulff et al. 2023, doi:10.1007/s40979-023-00146-z; Liang et al. 2023, doi:10.1016/j.patter.2023.100779 |
| L3 | Performance during instruction is not the same as durable learning. | 1, 2 | Learning-science literature | have (2011, 2013); to verify (1992) | Bjork and Bjork 1992, 2011; Bjork, Dunlosky and Kornell 2013 |
| L4 | A report of evidence, weighed by the instructor, keeps the assessment judgment with the instructor; a verdict or score would take it away. | 1, 2 | Design argument; ethics literature | have | Preprint §5.3 ("the instructor as meta-model"); Slade and Prinsloo 2013 |
| L5 | Inferring something about a learner from observed behavior is an evidence-centered design argument. | 1 | ECD literature | have | Mislevy, Steinberg and Almond 2003 |
| L6 | Keystroke and process logs can separate authentic from non-authentic writing in controlled settings. | 1, 2 | Peer-reviewed studies | have | Jiang et al. 2024; Deane et al. 2025; Crossley et al. 2024 |
| L7 | Autograders check correctness, not how the work developed. | 1 | Tool papers | to verify | Gradescope (Singh et al. 2017); Web-CAT (Edwards and Pérez-Quiñones 2008) |
| L8 | Writing-process capture products document who produced text, not how a project developed. | 1 | Current product documentation | to verify | Grammarly Authorship and Turnitin Clarity product pages |
| L9 | Student commit histories have been mined in computing education. | 1, 2 | Peer-reviewed studies | to verify | Mierle et al. 2005; Edwards et al. 2009; recent work |

## Design claims (Paper 1, relied on by Paper 2)

| ID | Claim | Paper | Evidence needed | Status | Source |
|---|---|---|---|---|---|
| D1 | Frictional is an auditor, not a grader: reports contain no verdicts or grade-determining scores. | 1, 2 | Report schema with no verdict or score fields; a test that rejects them | to collect | Brief (reframing 1) |
| D2 | One report carries artifact evidence (stem-project-review's lenses) and process evidence (repository dimensions, plus the Frictional starter set where evidence exists). | 1, 2 | The dimension list; a benchmark report showing both families | to collect | Bear, 2026-11-22; `PROJECT.md` |
| D3 | Dimensions are open modules, each with a versioned dimension card. | 1 | A card for every dimension | to collect | Brief (reframing 2; supporting components) |
| D4 | Deterministic facts come from scripts; the model handles interpretation only; each finding records its source. | 1 | Code structure; `source` field; RQ4 determinism result | to collect | Brief (reframing 4) |
| D5 | All dimensions are on by default; hidden dimensions remain listed, so missing evidence appears as missing. | 1, 2 | Render tests; benchmark check | to collect | Brief (report design) |
| D6 | Every report records the skill version and the model name and version. | 1, 2 | Schema; report header | to collect | Brief (report design) |
| D7 | Install-test failures include the agent's full transcript, distinguishing documentation failures from agent-environment failures. | 1 | Benchmark cases A3, A4 | to collect | Brief (report design) |
| D8 | Frictional runs locally and sends no data to Irreducibly Human. | 1, 2 | Source review (no outbound calls beyond the user's own clone); a network-isolated test; the README notice | to collect | Brief (reframing 3; README notice) |
| D9 | Field profiles recommend dimension configurations by CIP code, as versioned files. | 1, 2 | Profile files; the CIP edition used | to collect; CIP edition to verify | Brief (supporting components) |
| D10 | Instructor feedback goes through a pre-filled link with enumerated values only; agents do not submit feedback. | 1, 2 | Feedback design; a test of the link contents | to collect | Brief (supporting components) |

## Paper 1 result claims

| ID | Claim | Paper | Evidence needed | Status | Source |
|---|---|---|---|---|---|
| P1-1 | Per-dimension detection and false-positive rates on seeded issues (RQ1) | 1 | Scored audits of the frozen benchmark | to collect | [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md) |
| P1-2 | Confound cases receive the correct alternative explanations and no misleading interpretation, at a measured rate (RQ2) | 1 | Scored B cases | to collect | Benchmark spec |
| P1-3 | Manufactured process is reported for what the evidence shows; fully backdated histories cannot be shown false from git alone, only with an external push record (RQ3) | 1 | Scored C cases, with and without push evidence | to collect | Benchmark spec, C1 |
| P1-4 | Script facts are identical across runs and providers; model interpretations agree at a measured rate (RQ4) | 1 | Repeated runs across providers | to collect | Brief |
| P1-5 | An audit costs a measured amount of time and tokens per repository, by size and provider (RQ5) | 1 | Run logs; dated prices | to collect | Brief |
| P1-6 | Expected findings were frozen before any audit ran. | 1 | Git tag, hashes, timestamps | to collect | Brief (benchmark rules) |
| P1-7 | The benchmark is released as a public test and regression suite. | 1 | Public repository | to collect | Brief |
| P1-8 | Detecting synthetic patterns does not guarantee detecting real ones (the analogue of the coupling effect in mutation testing). | 1, 2 | Mutation-testing literature; Paper 2 comparison | to verify (references) | DeMillo, Lipton and Sayward 1978; Offutt 1992; Just et al. 2014 |
| P1-9 | The audit's aim is to make gaming visible, not to be ungameable. | 1 | Design stance; RQ3 results | to collect | Brief ("what carries over") |

## Paper 2 result claims

| ID | Claim | Paper | Evidence needed | Status | Source |
|---|---|---|---|---|---|
| P2-1 | The study was reviewed by Northeastern's IRB (protocol number, category). | 2 | IRB letter | to collect | [irb-protocol-notes.md](../process-evidence-in-practice/irb-protocol-notes.md) |
| P2-2 | Consent was opt-in, collected by a third party; the instructor learned who consented only after grades; analysis followed grades. | 2 | Honest-broker records; dates | to collect | Brief |
| P2-3 | Per-dimension finding precision on real work, by instructor and TA markings, with agreement (RQ1) | 2 | Markings | to collect | Brief |
| P2-4 | Findings changed the instructor's assessment in a measured share of submissions (RQ2) | 2 | Two-pass decision logs | to collect | Brief |
| P2-5 | The report added (or saved) a measured amount of review time (RQ3) | 2 | Timed records | to collect | Brief |
| P2-6 | Dimension enablement and relevance differ by field and level (RQ4) | 2 | Configuration logs; ratings | to collect | Brief |
| P2-7 | Confounds occur at measured rates in real work, and reports handled them at a measured rate (RQ5) | 2 | Markings; optional survey | to collect | Brief |
| P2-8 | False positives do or do not cluster by work style (RQ6) | 2 | IRB-approved method | to collect, if approved | Brief |
| P2-9 | Synthetic detection (Paper 1) carried over, or did not, to real precision per dimension | 1, 2 | P1-1 compared with P2-3 | to collect | This outline |
| P2-10 | Audit findings were never the sole basis for a grade or academic-integrity action. | 2 | Course policy; decision logs | to collect (policy to write) | Brief (auditor, not grader) |
| P2-11 | Process findings add prediction of a delayed, proctored, unannounced transfer check beyond artifact quality (optional secondary analysis) | 2 | Transfer check; findings; artifact scores; pre-registration | to collect, if kept | Preprint Claim 02, recast; review 2026-11-22 |

## Preprint claims cut or moved

| ID | Preprint claim | Status | Reason | Source |
|---|---|---|---|---|
| X1 | Claim 01: genuine learning at each cognitive tier leaves friction traces arising from the neurological processes that constitute learning. | cut | Not testable as stated; the audit reports evidence without claiming its neural cause. | Preprint abstract; review |
| X2 | BDNF expression is upregulated as much as 2.8-fold during moderate cognitive challenge. | cut | Traced to one 2026 review (Gkintoni et al., doi:10.3390/mti10010005). None of its six cited studies measured BDNF. | [source/references-verified.md](source/references-verified.md) |
| X3 | Dendritic spine formation increases 37% under moderate cognitive load. | cut | Same source; spine formation cannot be measured in living humans by the cited methods. | Same |
| X4 | An AI cannot produce the behavioral traces that learning leaves, because the events did not occur. | cut | Traces can be simulated (benchmark C3); replaced by P1-9. | Preprint §3.1; review |
| X5 | Claim 03: gaming all seven components costs about as much as learning. | cut | Agentic tools can manufacture several traces at once; replaced by "make gaming visible" (P1-9). | Preprint §5.1, §8; brief |
| X6 | The GLP probability score with a credible interval, from a three-layer ensemble | moved to future work | No data to fit it; "credible interval" implies a Bayesian model the ensemble is not. | Preprint §4–5; brief |
| X7 | Validation using academic integrity cases, and a "confirmed genuine" class defined by the same components the model scores | cut | Ethically fraught, selection-biased, and circular | Preprint §7.1; review; brief |
| X8 | "The GLP framework implementation, labeled corpus, and assessment design templates are published openly at irreduciblyhuman.com." | cut, and fix on the live preprint | No labeled corpus exists. | Preprint §10 |
| X9 | Tier calibration with seven numbered tiers | cut | Replaced by unnumbered facets where facets are used at all. Field profiles now key on CIP codes. | Preprint §6; brief |
| X10 | AI-generated audio "can already be processed to be spectrographically indistinguishable from professional human recordings." | cut or source | No citation; not needed by either paper | Preprint §1 |
| X11 | "In writing [the forensic window] is largely closed already. In code it is closing." | to verify, or soften | Needs detector studies for each domain; L2 supports writing only | Preprint §1 |
| X12 | "Students learn to game the detector … the simulation gets better over time as students share strategies." | to verify, or soften | No citation | Preprint §2.2 |
| X13 | Claim 02: traces are partly independent of artifact quality and add information. | recast as P2-11 (secondary) | Testable only against an independent criterion | Preprint; review |
| X14 | Claim 04: a second evidence stream the instructor weighs | kept as L4 and D2 | A design stance; needs no data | Preprint; brief |
