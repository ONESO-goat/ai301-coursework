# Rubric: is this pull request ready to submit?

<!--
THIS IS THE PART YOU WRITE (fourth week running; this is the rubric's
final form in the sandbox). Your frame in SKILL.md executes whatever
checks you define here, via your procedure.md. It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the diff read against the plan's scope, the test
     evidence read against the plan's test plan, the description read
     against the diff, the repo-facts block's template asks) or a
     location from your references/evidence-guide.md. "The PR" is not
     a source; "the diff's changed files read against the plan's
     stated boundary" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself
     (does the diff fall inside the plan plus its deviation notes? is
     the claimed evidence observable?), never the write-up's shape
     (how long the description is, how many commits there are).
     Structure-shaped checks are what make graders disagree with
     themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (submit) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. State the `unclear`
   treatment explicitly: the frame here is YOUR SKILL.md, so a rubric
   that stays silent is only covered if your frame's grading
   discipline says what happens (the contract's own default is that
   an unverifiable claim fails).

Cover what actually gets bad PRs submitted. The failure families the
lecture named ARE the harness's scoring categories, same names as the
eval README: silent drift (the diff silently does more or less than
the posted plan, or the description claims fidelity the diff
contradicts), not tested (the evidence proves nothing observable, or
the repo's own checks were never run), unreviewable (debris or
unrelated hunks bury the change), and standards wall (the repo's
stated template and disclosure asks are ignored). Your evidence
guide's four headings map onto these one to one (plan fidelity =
silent drift, test evidence = not tested, diff quality =
unreviewable, standards and comms = standards wall), and the category
floor is scored on exactly these names plus clear accept. A rubric
that ignores a category will fail the eval packages built around
that category. And remember the honest-outcome
rule, fourth week running: a PR that honestly discloses a shortfall
can be ready; a rubric that equates "less than everything" with
"hold" fails the set.
-->

## Checks


| Check | Evidence | Pass condition | Weight |
| --- | --- | --- | --- |
| **plan-fidelity** | The diff (`git diff main...HEAD`) read against `plan.md` and any notes under `## Deviations` | Passes if every change in the diff is authorized by the plan or explicitly disclosed and justified as a deviation. | required |
| **test-coverage** | The `test_evidence.md` file read against the repo's required checks and repro steps | Passes if all required checks (`make test-unit`, etc.) and repro steps are run and honestly reported, with no hidden failures. | required |
| **diff-cleanliness** | The diff (`git diff main...HEAD`) read against the workspace files | Passes if the diff contains no debug prints, stray console logs, commented-out dead code, or unrelated refactoring. | required |
| **standards-compliance** | The PR description (`pr_draft.md`) read against Path Review's template and contribution docs | Passes if every section of the template is filled out, the issue number is correctly linked, and the mandatory AI-use disclosure is present. | required |
| **regression-check** | The testing section of the PR description | Passes if both before and after behavior are demonstrated for the repro steps. | preferred |

### Verdict Rule

> **Accept (submit)** if and only if all `required` checks pass (`P`). Any `required` check graded fail (`F`) or unclear (`?`) results in **Reject (hold)**. Unclear claims are treated as failing because unverified evidence cannot be accepted. `preferred` checks are advisory only.

