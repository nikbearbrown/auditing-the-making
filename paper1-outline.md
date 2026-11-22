> **Provenance.** Drafted by Claude Code, model Claude Opus 5.5 (`claude-opus-5-5`), on 2026-11-22. Phase 1 deliverable: outline of Paper 1. Not a draft of the paper.
>
> **Human sign-off** (left blank until a human fills it in)
> Name: ____________ Date: ____________ Decision (approved / approved with changes / rejected): ____________ Notes: ____________

# Paper 1 outline: the audit tool, evaluated on synthetic data

## Executive summary

**What this is:** a section-by-section outline of Paper 1. For each section it gives the claims the section would make and the evidence each claim needs. It also covers title options, research questions, figures, the evaluation plan, threats to validity, related work (with verification status), candidate venues, and numbered open decisions.

**Why read it:** Paper 1 asks one question: does the Frictional auditor detect what it claims to detect? It answers with a synthetic benchmark only, so no human subjects are involved and no IRB approval is needed. Everything Paper 1 can and cannot claim follows from that choice.

**What it decides and leaves open:**
- **Decided by the brief:** five research questions, synthetic data only, expected findings frozen before any audit runs, and an explicit limitation. Synthetic data can establish detection accuracy. It cannot establish that detected patterns match real student behavior, or that findings help instructors; Paper 2 addresses those.
- **Has today:** the design stance, the preprint's argument (with the parts the brief retires removed), a verified reference base, and the stem-project-review machinery to build on.
- **Does not have:** the skill, the benchmark, or any results. Every Results claim is "to collect".
- **Left for you:** the title, the benchmark scale, the model providers, the venue, and how this paper is sequenced with classroom use in Spring 2027 (decisions 1 to 11).

## Title options

1. **Auditing the Making: An Agent-Run Tool for Evidence of How Student Work Was Made** (working title)
2. Frictional: An Agent-Run Audit of How Student Work Was Made, Evaluated on a Synthetic Benchmark
3. Evidence, Not Verdicts: Evaluating an Agent-Run Process Audit of Student Repositories
4. Does the Auditor See What It Claims? A Synthetic Benchmark for Auditing How Student Work Was Made
5. Making Gaming Visible: Design and Synthetic Evaluation of an Agent-Run Process Audit

## Contribution statement

Generative AI can produce the artifacts that courses use as evidence of learning, so instructors need evidence of how a piece of work was made, not only of what it contains. This paper presents Frictional, a skill that a user's own AI agent runs locally against a folder or GitHub repository. It reports two streams of evidence side by side, across modular dimensions. Artifact dimensions say what the work is and whether it does what it claims: purpose, install and run, correctness, tests, reproducibility, scientific claims and documentation. These are carried over from an existing project-review skill. Process dimensions say how the work was made: commit history, an install test that follows the README, naming, README completeness, repository hygiene, contribution distribution, and a starter set carried over from earlier work on process friction traces. The process dimensions are reported wherever their evidence exists. Each dimension is documented in a versioned dimension card. Deterministic facts come from scripts, and interpretation comes from the model, with each finding labeled by its source. The report gives neutral observations with alternative explanations and no verdicts. We evaluate Frictional on a synthetic benchmark of [N] cases in three categories (straightforward patterns, deliberate confounds, adversarial cases), with expected findings frozen before any audit was run. We measure:
- detection and false-positive rates per dimension;
- whether confound cases receive the correct alternative explanations;
- whether manufactured process is reported for what it is;
- consistency across repeated runs and model providers, separately for script and model findings;
- cost per repository.

The benchmark is released as a public test and regression suite. Synthetic evaluation establishes what the auditor can detect; it does not show that the patterns occur in real student work, or that the reports help instructors.

## Research questions

- **P1-RQ1:** For each dimension, how accurately does the audit detect pre-specified, seeded issues (detection rate and false-positive rate)?
- **P1-RQ2:** On deliberate confound cases, does the report offer the correct alternative explanations rather than a misleading interpretation?
- **P1-RQ3:** Does the audit detect manufactured process, such as backdated commits pushed all at once?
- **P1-RQ4:** How consistent are findings across model providers and across repeated runs of the same model, reported separately for script-based and model-based findings?
- **P1-RQ5:** What does an audit cost per repository in runtime and tokens?

## Section-by-section outline

Status key for evidence: **have** (exists now), **to collect** (Paper 1 must produce it), **to verify** (a source exists but has not been confirmed).

### 1. Introduction

| Claim | Evidence needed | Status |
|---|---|---|
| Generative AI weakens the inference from an artifact to the process that produced it. | The decoupling argument (preprint §1 to 2); studies showing output-only AI-text detectors are unreliable and biased (Weber-Wulff et al. 2023; Liang et al. 2023) | have |
| Instructors need evidence of how work was made that they can weigh themselves; a verdict or score would take that judgment from them. | The design argument (preprint §5.3, "the instructor as meta-model"); the learning-analytics ethics literature (Slade and Prinsloo 2013) | have |
| Existing tools check correctness (autograders) or document who produced text (writing-process capture), not how a project developed. | Related work: Gradescope, Web-CAT, Grammarly Authorship, Turnitin Clarity | to verify (§2) |
| Contributions: (1) the tool design; (2) a frozen-expectation synthetic benchmark, released; (3) an evaluation answering RQ1 to RQ5. | The paper itself | to collect |

### 2. Background and related work

| Claim | Evidence needed | Status |
|---|---|---|
| Arguing from observed behavior to a claim about a learner is an evidence-centered design problem; Frictional supplies evidence and leaves the claim to the instructor. | Mislevy, Steinberg and Almond 2003 | have (verified) |
| Process data have long been used to assess learners unobtrusively, and to detect students gaming a system. | Shute 2011; Baker et al. 2004; Corbett and Anderson 1994 or 1995 | have (verified) |
| Keystroke and process logs can separate authentic from non-authentic writing in controlled settings. | Leijten and Van Waes 2013; Jiang et al. 2024; Deane et al. 2025; Crossley et al. 2024 | have (verified) |
| Commit histories and submission timing have been mined in computing education for performance and behavior. | Mierle et al. 2005; Edwards et al. 2009; recent work (2023 to 2026) | to verify |
| Autograders assess correctness, not process. | Gradescope (Singh et al. 2017); Web-CAT (Edwards and Pérez-Quiñones 2008) | to verify |
| Model cards and datasheets document a model or dataset's intended use and limits; dimension cards apply this to audit dimensions. | Mitchell et al. 2019; Gebru et al. 2021 | to verify |
| Seeded faults are a proxy for real faults whose validity rests on the coupling effect; the same caution applies to synthetic process patterns. | DeMillo, Lipton and Sayward 1978; Offutt 1992; Just et al. 2014 | to verify |
| LLM judgments vary across runs and providers, so consistency must be measured, not assumed. | Literature on LLM-as-judge reliability | to verify |

### 3. Frictional: design

| Claim | Evidence needed | Status |
|---|---|---|
| Frictional is an auditor, not a grader: reports contain observations, alternative explanations and missing-evidence markers, and no scores or verdicts. | The report schema (no verdict or score fields); a schema test that rejects them | to collect (skill not yet built) |
| One report carries both evidence streams the preprint argued for: artifact dimensions (stem-project-review's review lenses) and process dimensions (repository history and conventions, plus the Frictional starter set where evidence exists). The instructor weighs them. | The dimension list; a report on a benchmark case showing both families | to collect |
| Dimensions are modules, each with a versioned card (what it checks, data needed, known confounds, example finding, version). | Dimension cards for every dimension in the benchmark | to collect |
| Checkable facts come from scripts; only interpretation comes from the model; each finding records its source. | Code structure; the `source` field on every finding; RQ4's determinism result for script facts | to collect |
| All dimensions are on by default; a dimension the instructor hides is still listed by name, so missing evidence appears as missing. | Rendering tests; benchmark checks (`hidden_dimensions_listed_by_name`) | to collect |
| Every report records the skill version and the model name and version. | Schema and report header | to collect |
| Install-test failures include the agent's full transcript, so a documentation failure can be told apart from an agent-environment failure. | Benchmark cases A3 and A4; transcript attachment | to collect |
| Frictional sends no data to Irreducibly Human; the user's agent processes the work. | Source code (no outbound calls other than the user-initiated clone); a network-isolated test run; the README notice | to collect |
| Field profiles keyed by CIP code recommend which dimensions to show. | Versioned profile files; the CIP source and version | to collect; CIP edition to verify |
| Instructor feedback goes through a pre-filled link with enumerated values only; agents do not submit feedback. | The feedback form design; a test that the link contains only enumerated values | to collect |
| The design reuses an existing two-view report pattern (people and agents) and the artifact review lenses of an existing project-review skill. | stem-project-review (`report.md` and `report.json`, schema, validate and render, rubric lenses). It is unpublished, so cite it as software with a commit or release. | have |

### 4. The synthetic benchmark

| Claim | Evidence needed | Status |
|---|---|---|
| The benchmark covers every dimension with at least one seeded issue, and includes confounds and adversarial cases. | [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md) scenario table, as built | to collect |
| Expected findings were frozen before any audit ran. | Git tag, frozen-file hashes, timestamp; audit logs dated after the freeze | to collect |
| Each case is labeled by how it was made; scripted human-style histories are never labeled human. | Case metadata | to collect |
| A hold-out set built by someone other than the tool's author limits tuning to the test. | Hold-out provenance; results reported separately for hold-out and development cases | to collect |

### 5. Evaluation method

| Claim | Evidence needed | Status |
|---|---|---|
| Detection, false-positive, alternative-explanation and consistency scores follow pre-specified rules. | Scoring rules in the benchmark spec, frozen with the expectations | to collect |
| Where scoring needs judgment, two raters score blind to model and run; agreement is reported. | Rater protocol; agreement statistics | to collect |
| Providers and versions, run counts, sandbox, and dates are fixed and reported. | Run manifest | to collect |

### 6. Results (one subsection per research question)

| Claim | Evidence needed | Status |
|---|---|---|
| RQ1: detection and false-positive rates per dimension, script and model separately | Scored audits | to collect |
| RQ2: share of confound cases with the correct alternatives and no misleading interpretation | Scored confound cases | to collect |
| RQ3: which manufactured patterns were reported correctly, and which evidence was missing when they were not | Scored adversarial cases | to collect |
| RQ4: script facts identical across runs and providers (any difference reported as a defect); agreement on model interpretations | Repeated runs | to collect |
| RQ5: runtime and tokens per repository, by size and provider, with prices and the date | Run logs | to collect |

### 7. Discussion

| Claim | Evidence needed | Status |
|---|---|---|
| The aim is to make gaming visible, not to be ungameable. Some manufactured histories (C1) cannot be detected from git alone, only through evidence collected outside the student's control. | RQ3 results; the C1 design | to collect |
| Synthetic detection does not guarantee real detection; as with the coupling effect in mutation testing, the link has to be tested on real faults, which is Paper 2's job. | Mutation-testing literature; Paper 2 design | to verify |
| Where model interpretations vary across runs, instructors should rely on script facts and treat interpretations as prompts for their own reading. | RQ4 results | to collect |

### 8. Threats to validity

Listed in full below.

### 9. Ethics, availability and limitations

| Claim | Evidence needed | Status |
|---|---|---|
| No human subjects were involved; no student work was used or imitated. | Case provenance records | to collect |
| The skill and the benchmark are released, with licenses stated. | Repository and license | to collect; license is an open decision |

### 10. Conclusion

A summary of what the evaluation showed and what it cannot show, pointing to Paper 2.

## Carried over from the preprint, and retired

| Preprint element | In Paper 1 |
|---|---|
| Decoupling argument; the Bjork distinction between performance and learning; the instructor as final judge; the ethics of support versus surveillance | Kept (§1, §3, §9) |
| Seven friction components | Kept as starter dimensions with cards. Only Y₁, Y₂ and Y₅ (as `temporal-engagement`, `error-trajectory`, `process-log`) are exercised by the benchmark; the rest are reported as `no_evidence`. |
| GLP probability composite and three-layer ensemble | Moved to future work |
| BDNF 2.8-fold and dendritic spine 37% figures | Removed. They trace to one 2026 review whose cited studies do not measure them ([source/references-verified.md](source/references-verified.md)). |
| "Gaming all components costs as much as learning" | Replaced by "make gaming visible" (RQ3, §7) |
| Validation with academic integrity cases | Removed |
| "Tier" | Replaced by "facet", unnumbered |

## Planned figures and tables

| # | Kind | Content | Section |
|---|---|---|---|
| F1 | Figure | Data flow: the user's agent, the skill, scripts and model, the local report; nothing goes to Irreducibly Human | §3 |
| F2 | Figure | An excerpt of a real report for synthetic case B2, showing the facts section, the interpretations section with alternatives, and a dimension marked `no_evidence` | §3 |
| T1 | Table | Dimension cards in brief, grouped by family (artifact; process: repository; process: Frictional starter): dimension, data needed, script facts, model interpretation, known confounds, version | §3 |
| T2 | Table | Benchmark scenarios by category, origin, construction method and variant counts | §4 |
| T3 | Table | RQ1: detection and false-positive rate per dimension, script and model | §6 |
| T4 | Table | RQ2: confound cases, alternatives offered, misleading interpretations made | §6 |
| T5 | Table | RQ3: adversarial cases, evidence present or absent, correct or incorrect reporting | §6 |
| F3 | Figure | RQ4: agreement across runs and providers, script versus model findings | §6 |
| T6 | Table | RQ5: runtime and tokens per repository, by size and provider, with dated prices | §6 |

## Evaluation plan and metrics

- **Cases:** per [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md); about 126 at full scale (open decision 3).
- **Runs:** each case audited 5 times with each provider (Claude and Gemini, plus or minus a third). Model and version are pinned and recorded. Temperature or equivalent settings are recorded where the agent exposes them.
- **RQ1 metrics:** detection rate (detected expected facts / expected facts), per dimension; false-positive rate (findings matching a guard or not implied by the construction / total findings), per dimension; 95% confidence intervals by case-level bootstrap.
- **RQ2 metrics:** alternative-explanation coverage (offered / required) per confound case; misleading-interpretation rate (cases with any `must_not_assert` / confound cases).
- **RQ3 metrics:** correct-evidence reporting rate on adversarial cases; over-claim rate (detection claimed without supporting evidence).
- **RQ4 metrics:** for script facts, the proportion identical across all runs and providers (expected 100%; anything less is a bug, investigated and reported). For model interpretations, percent agreement and Krippendorff's alpha on the presence of each expected interpretation, within one provider across runs and across providers.
- **RQ5 metrics:** median and range of wall-clock time, sandbox time, and input and output tokens per audit, by size and provider; cost at list prices on a stated date.
- **Raters:** two, blind to provider and run, for judgment-dependent scoring; disagreements resolved by discussion and reported.

## Threats to validity

| Threat | Kind | Mitigation |
|---|---|---|
| Synthetic patterns may not resemble real student behavior; scripted human-style histories encode the author's assumptions. | Construct, external | State it as the central limitation; Paper 2 measures finding precision on real work. Use published patterns where they exist. |
| The tool's author also built the benchmark, so the tool may be tuned to its own test. | Internal | Freeze expectations before audits; hold-out cases built by someone else; report development and hold-out results separately. |
| Scoring "not implied by construction" involves judgment. | Construct | Two blind raters; report agreement; publish the scored outputs. |
| Model versions change; results describe the versions tested. | External, reliability | Record exact versions and dates; the regression suite allows re-running. |
| Prompt and skill-version sensitivity | Reliability | Fix the skill version per run set; report it. |
| Install-test outcomes depend on the sandbox (operating system, network, preinstalled tools). | Internal | Fixed sandbox image, recorded; transcripts released. |
| Coverage is limited to chosen languages, sizes and GitHub-hosted git. | External | Report coverage; the benchmark is extensible. |
| Starter dimensions Y₃, Y₄, Y₆ and Y₇ are not evaluated. | Construct | Say so; they need course data (Paper 2). |
| Cost figures date quickly. | External | Report tokens as well as prices, with the date. |
| C1 detection depends on evidence outside git (push events, CI), which not every user will have. | External | Report results with and without that evidence. |

## Related-work map

Status: **verified** (checked against Crossref or the publisher on 2026-11-22), **verifying** (check in progress), **UNVERIFIED** (not confirmed; do not cite until checked).

| Area | Reference | Use in Paper 1 | Status |
|---|---|---|---|
| Assessment argument | Mislevy, Steinberg and Almond (2003), *Measurement* 1(1), 3–62, doi:10.1207/S15366359MEA0101_02 | §2 framing | verified |
| Stealth assessment | Shute (2011), in Tobias and Fletcher (Eds.), *Computer Games and Instruction*, 503–524 | §2 | verified |
| Gaming the system | Baker, Corbett, Koedinger and Wagner (2004), CHI 2004, 383–390, doi:10.1145/985692.985741 | §2 | verified |
| Knowledge tracing | Corbett and Anderson (1994 or 1995), *UMUAI* 4(4), 253–278, doi:10.1007/BF01099821 | §2 | verified (year differs by source) |
| Keystroke logging | Leijten and Van Waes (2013), *Written Communication* 30(3), 358–392, doi:10.1177/0741088313491692 | §2 | verified |
| Keystroke-based detection of non-authentic text | Jiang et al. (2024), *JEM* 61(4), doi:10.1111/jedm.12416; Deane et al. (2025), *JEM* 63(1), doi:10.1111/jedm.12431; Zhang et al. (2025), *EM:IP* 44(2), doi:10.1111/emip.12668; Crossley et al. (2024), EDM 2024, doi:10.5281/zenodo.12729864 | §2, closest prior work | verified |
| Output-only detectors | Weber-Wulff et al. (2023), *IJEI* 19, 26, doi:10.1007/s40979-023-00146-z; Liang et al. (2023), *Patterns* 4(7), 100779, doi:10.1016/j.patter.2023.100779 | §1 | verified |
| Writing-process capture products | Grammarly Authorship; Turnitin Clarity (product pages) | §1, §2 | verified as product pages; feature claims need checking against current pages |
| Learning analytics ethics | Slade and Prinsloo (2013), *American Behavioral Scientist* 57(10), 1510–1529, doi:10.1177/0002764213479366 | §1, §9 | verified |
| Performance versus learning | Bjork and Bjork (1992), in Healy, Kosslyn and Shiffrin (Eds.), vol. 2, 35–67; Bjork and Bjork (2011), *Psychology and the Real World*, 56–64 | §1 | 2011 verified; 1992 verifying |
| Commit-history mining | Mierle et al. (2005), MSR; Edwards et al. (2009), ICER; 2023–2026 work | §2 | verifying |
| Autograders | Singh et al. (2017), Gradescope, L@S; Edwards and Pérez-Quiñones (2008), Web-CAT, ITiCSE | §2 | verifying |
| Mutation testing and coupling | DeMillo, Lipton and Sayward (1978), *IEEE Computer*; Offutt (1992), *TOSEM*; Just et al. (2014), FSE | §2, §7 | verifying |
| Model cards and datasheets | Mitchell et al. (2019), FAT*; Gebru et al. (2021), *CACM* | §3 | verifying |
| LLM-as-judge variability | to be identified | §2, §7 | verifying |

## Candidate venues

*To be filled in from the venue and library-coverage check in progress; each entry will carry its date checked.* Already verified on 2026-11-22 (see `process-evidence-in-practice/README.md`):
- SIGCSE TS 2027 had an "Experience Reports and Tools" track: 6 pages plus 1 page of references; abstracts June 26 and papers July 3, 2026. The 2028 dates are not announced.
- ITiCSE 2027 (Glasgow, July 12 to 14): abstract January 11, paper January 18, 2027.
- Koli Calling 2026: 10-page full papers, due July 12 (extended to July 19), 2026. 2027 is not announced.

## Open decisions

1. **Title.** Options above. Tradeoff: naming the tool ("Frictional:") aids discovery and citation; a question title signals the evaluation.
2. **Which dimensions Paper 1 evaluates.** (a) Artifact dimensions, repository process dimensions, and process-log, error-trajectory and temporal-engagement (as specified); (b) repository process dimensions only, which is simpler and faster to build, but under-describes a tool that also reviews the artifact; (c) all, with Y₃ to Y₇ shown only as `no_evidence`. Tradeoff: scope against build time before Spring 2027.
3. **Benchmark scale.** See [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md), open decision 1.
4. **Model providers.** Claude and Gemini, or add a third. Tradeoff: generality against cost (about 630 more runs per provider).
5. **Venue and timing.** (a) ITiCSE 2027, January 18, 2027: requires the skill, benchmark and results in 8 weeks, which is not realistic with the IRB work also due. (b) SIGCSE TS 2028 Experience Reports and Tools, expected early July 2027: time for a full benchmark. (c) Koli Calling 2027, expected mid-July 2027: longer page limit. (d) ACM TOCE: no deadline, longer form, slower. Coverage of publication charges is still being verified.
6. **Sequencing with Paper 2.** The tool should pass benchmark v1 before it is run on any student work in Spring 2027. Options: (a) benchmark v1 by early February, and classroom audits start with the first assignment due after that; (b) classroom audits start after midterm. Tradeoff: Paper 2's sample size against having validated the tool first.
7. **Benchmark release and double-blind review.** Release through an anonymized link during review, or after acceptance.
8. **Install-test sandbox.** See `PROJECT.md` open decision 5.
9. **Licenses.** For the skill (for example MIT) and the benchmark (for example CC BY 4.0 for case data, MIT for builders and scorer). Who the rights holder is (Humanitarians AI, Bear Brown, LLC, or the author) is also open.
10. **Authorship and affiliation order.**
11. **Whether Paper 1 names any course.** The benchmark is synthetic, but describing the motivating courses identifies the author's courses. Usually fine; state it deliberately.
12. **Severity and recommended fixes on artifact findings** (from stem-project-review). Keep them, soften severity to "effect on the stated claim", or drop them. See `PROJECT.md` open decision 7.
