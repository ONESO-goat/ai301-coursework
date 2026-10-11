# Evidence guide: where evidence lives in a PR package

<!--
THIS IS THE PART YOU WRITE (third week running: the map stays in your
hands). Your tool uses this guide as its map: for every kind of
evidence a rubric check names, this file says WHERE to find it in a PR
package and WHAT GOOD LOOKS LIKE when you do.

The four families below are the harness's failure categories under
the names the eval README uses: plan fidelity = silent-drift, test
evidence = not-tested, diff quality = unreviewable, standards and
comms = standards-wall. A package that fails none of them is a
clear-accept. Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the plan-context block's scope pair and test
  plan, the candidate PR's diff, commits, description, or
  test-evidence section, the repo-facts block's template asks and
  stated policy). In live mode (where in your working copy and on
  GitHub: your plan.md and its deviation notes, your branch's diff,
  your draft title and description, your captured test output, the
  repo's PR template and CONTRIBUTING.md).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("every changed file falls inside the
  plan's stated boundary or a deviation note") over adjectives ("the
  diff is clean").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts three ways: your
procedure says WHEN to gather each family, this guide says WHERE, and
your SKILL.md says the tool reads both. Write the map you wish your
executor had.
-->

## Plan fidelity (harness category: silent-drift)

* **Where it lives:** In an eval bundle, look in the plan-context block's scope section (and any `## Deviations` notes), compared against the candidate PR's diff hunks. In live mode, look in your working copy's `plan.md` under its scope and deviation notes, and compare it against your branch's diff produced by `git diff main...HEAD`. The PR description's summary and changes sections read against the diff also live here.
* **What good looks like:** Every changed file and code hunk falls strictly inside the plan's stated boundary or is explicitly authorized under an honest `## Deviations` note. The changes match the plan's proposed solution without unstated additions or omissions.

## Test evidence (harness category: not-tested)

* **Where it lives:** In an eval bundle, find this in the package's test-evidence section and commit messages. In live mode, look in `test_evidence.md` next to your `plan.md`, containing your re-run Unit 2 repro steps (before and after) and the outputs from the repo's required checks (`make test-unit`, `make test-lint`, `make test-typecheck`).
* **What good looks like:** The evidence explicitly shows observable before-and-after behavior for the repro steps, alongside visible, non-hidden outcomes for all required repo checks demonstrating the bug is fixed and no regressions were introduced.

## Diff quality (harness category: unreviewable)

* **Where it lives:** In an eval bundle, look across the whole unified diff and the commit list. In live mode, look at the output of `git diff main...HEAD` and `git diff main...HEAD --stat`.
* **What good looks like:** The diff cleanly isolates the bugfix and its corresponding tests, containing zero debugging artifacts, console prints, dead or commented-out code blocks, formatting churn, or unrelated drive-by refactoring.

## Standards and comms (harness category: standards-wall)

* **Where it lives:** In an eval bundle, check the repo-facts block's template asks and stated contribution policies. In live mode, look at `pr_draft.md` compared against `.github/PULL_REQUEST_TEMPLATE.md` and `docs/CONTRIBUTING.md` in your Path Review repo.
* **What good looks like:** Every section of the PR template is thoroughly filled with substantive content (such as proper issue references, detailed change bullets, and the mandatory AI-use disclosure) rather than boilerplate text or ignored checkboxes.