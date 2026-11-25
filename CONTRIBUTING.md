# Help write Auditing the Making

*Auditing the Making* evaluates the Frictional audit skill, an agent-run tool that reports evidence of how student work was made. The evaluation uses a synthetic benchmark only, with no human subjects.

**Where it stands:** there is an outline, a benchmark specification and a claims ledger. No part of the paper is drafted and no audit has been run on the benchmark. Some outline decisions are still open; they are listed at the end of [paper1-outline.md](paper1-outline.md).

**If you have an hour:** read one benchmark scenario in [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md) and [open an issue](https://github.com/nikbearbrown/auditing-the-making/issues/new) saying whether its expected finding is defined well enough that two people would agree on it.

## Pick a way to help

| Contribution | Where to start | What to send |
|---|---|---|
| **Review a benchmark scenario** | [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md) | Name the scenario. Say whether its expected finding is unambiguous, what variant is missing, or how the auditor could pass it for the wrong reason. |
| **Propose a missing scenario** | [synthetic-benchmark-spec.md](synthetic-benchmark-spec.md) | A realistic way student work gets made that the benchmark does not cover. Describe the project state and the finding a correct audit should report. |
| **Check a claim** | [claims-ledger.md](claims-ledger.md) | Pick one claim. Say whether the evidence listed would actually support it, and what else would be needed. |
| **Review the outline** | [paper1-outline.md](paper1-outline.md) | A missing argument, a threat to validity that is not listed, or a research question the evaluation cannot answer. |
| **Verify a reference or add related work** | [source/references-verified.md](source/references-verified.md) and the related-work map in the outline | A primary source link, page or table, and the claim it supports. References not yet confirmed are marked; confirming one is useful. |
| **Run the auditor** | The [Frictional skill](https://github.com/nikbearbrown/frictional) | Run it on a synthetic project you built and report what it found and missed. Describe how the project was constructed. |

## Rules for this repo

- **Synthetic data only.** Never add student work, grades, names or anything derived from a real submission. This paper has no human subjects.
- **Nothing is invented.** Mark a reference you could not confirm as unverified. Give the date you checked a venue fact.
- **Keep the tool and the paper separate.** Bugs and feature requests for the auditor go to the [skill repo](https://github.com/nikbearbrown/frictional).

## How to submit

For a discussion, [open an issue](https://github.com/nikbearbrown/auditing-the-making/issues/new) with the file or section, your evidence, and a proposed next step. For an edit, fork, branch, and open a focused pull request. Say what you changed and how you checked it. If you use an AI-generated answer, verify its citations and claims before submitting it.

If you want to collaborate beyond a single contribution, open an issue describing what you'd like to take on, and read [Credit and what we expect from authors](#credit-and-what-we-expect-from-authors) first.

## Credit and what we expect from authors

The author list isn't decided yet. We follow [Yale's guidance on authorship](https://provost.yale.edu/policies/academic-integrity/guidance-authorship-scholarly-or-scientific-publications). Under it, an author has done **all four** of these:

1. **Contributed to a component of the work:** its conception, design, conduct, analysis, or interpretation of at least part of the results.
2. **Helped write the paper:** drafted part of it, or revised it for substance, not just copy edits.
3. **Approved the final version** before submission.
4. **Agreed to be accountable** for the work, including helping answer questions about its accuracy or integrity.

Some contributions are valuable but don't by themselves make someone an author: a single issue, one verified reference, or reviewing a finished draft to offer suggestions. Everyone who contributes that way is thanked by name in the acknowledgments, unless they ask not to be. To be an author, take on a component, such as building and freezing a family of benchmark scenarios, running the evaluation for one research question, or owning the related-work section, and then do the writing, approval and accountability steps too. An AI model can't be an author, since it can't approve the paper or answer for it.

If you want to be an author, we expect you to:

- **Read the whole paper,** not just your section. You're putting your name on all of it.
- **Think about it, then give feedback.** Does the method answer the question? Are the comparisons fair? Do the numbers in the text match the tables, figures and data?
- **Suggest changes when they matter.** Don't make a suggestion just to have made one. If you find nothing to change, say so; that's a useful answer. A real problem, raised clearly with a proposed fix, is the most valuable thing you can give.
- **Disclose AI assistance.** AI tools are fine for code and drafting, but say where you used them. You stay accountable for everything you contribute.
- **Keep a record of what you did:** what, when, and where it lives (issue, pull request, commit, figure). The paper's contribution statement is drawn from it and lists each author's [CRediT roles](https://credit.niso.org/).
- **Sign off only when you can stand behind it.** Before submission, every author confirms in writing that they have read the full paper, agree with it, and accept accountability for it. If something is wrong or unclear, say so before approval, not after publication.

Raise authorship early, and we'll revisit it as roles change. Author order follows contribution. If you think your work merits authorship and it isn't reflected, say so before the final draft. Sending an issue or pull request does not by itself settle authorship.

## Licence

No licence has been chosen for this repo yet. Until one is, ask before reusing its text or data elsewhere.
