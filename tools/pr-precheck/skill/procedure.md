# Procedure: how this tool grades a PR package

<!--
THIS IS THE PART YOU WRITE (second week running for the procedure).
Week 3 you wrote these steps for a plan package; this week the graded
object is a PR package, and the read that matters most is a
side-by-side: the diff against the plan, the evidence against the test
plan, the description against both. Your week-3 procedure is the
pattern; do not paste it unchanged, because its read order was built
for a different object.

Your rotation is the design brief again, and this week friction routes
three ways: a stall on WHAT to decide is a rubric gap, a stall on
WHERE to look is a procedure gap (this file), and a stall on what the
tool even reads or outputs is a frame gap (your SKILL.md). A complete
procedure lets someone who has never seen a PR package before grade
one exactly the way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
plan's scope pair before opening the diff, and list the files the plan
names" is a step; "understand the change" is a wish.
-->


## Read order

1. Read the issue description first to understand the bug, reproduction steps, and expected behavior.
2. Read `plan.md` (and any `## Deviations` notes) next to understand the authorized scope, proposed changes, and test plan.
3. Read the branch diff (`git diff main...HEAD`) to see the actual code changes made in the PR.
4. Read `test_evidence.md` to review the executed test outputs, check results, and repro before-and-after data.
5. Read the draft PR description (`pr_draft.md`) last, comparing its claims, checklist, and disclosures against the actual diff and test evidence gathered in the previous steps.
6. Note down any mismatches between the plan and the diff, missing test evidence, or incomplete PR template sections during this initial read-through.

---

## Evidence gathering

1. **For Plan Fidelity (Silent Drift):** Gather the list of modified files from the diff (`git diff main...HEAD --name-only`) and compare them file-by-file against the files authorized in `plan.md`'s scope section and any documented deviations.
2. **For Test Evidence (Not Tested):** Extract the execution results for required checks (`make test-unit`, `make test-lint`, `make test-typecheck`) and the reproduced before-and-after outputs from `test_evidence.md`. Compare them against the test plan specified in `plan.md`.
3. **For Diff Quality (Unreviewable):** Scan the full diff (`git diff main...HEAD`) for debugging artifacts, console logs, commented-out dead code, or unrelated refactoring hunks.
4. **For Standards and Comms (Standards Wall):** Pull each section of `pr_draft.md` (Summary, Issue reference, Changes bullet list, Testing checkboxes, and Reviewer Notes / AI-use disclosure) and verify each against Path Review's template and contribution docs.

---

## Check execution

1. Execute checks in the order they appear in `rubric.md`: first plan fidelity, then test coverage, diff cleanliness, and standards compliance.
2. For each check, compare the gathered evidence against the specific pass condition defined in `rubric.md`.
3. If evidence for a specific check is entirely missing or unreadable from the package, grade that check as `unclear` (?) and record the reason. Never guess or improvise missing evidence.
4. If a check's required evidence is fully present and satisfies the pass condition, assign a grade of `pass` (P). If it violates the pass condition, assign `fail` (F).
5. Once a check's outcome is determined based on the explicit evidence and pass condition, do not re-read the entire package unless a conflicting piece of evidence is discovered in a later step.

---

## Verdict assembly

1. Apply the rubric's verdict rule: the package receives an `accept` verdict only if every `required` check is graded `pass` (P).
2. If any `required` check receives a `fail` (F) or `unclear` (?) grade, assign a `reject` verdict.
3. Report `preferred` checks for feedback, but exclude them from driving the binary verdict.
4. For the final output JSON block, when a package is accepted, list all checks with their passing evidence. When a package is rejected, identify the deciding check by selecting the **first failing required check in rubric order**, and quote the specific fact or line from the evidence that triggered its failure.