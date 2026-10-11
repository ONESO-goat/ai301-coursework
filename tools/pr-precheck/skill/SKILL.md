---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

## The question

Answer this single question: Is this candidate pull request ready to submit, or should it be held? A PR package consists of the target issue, the implementation plan (`plan.md` with any deviation notes), the branch diff (`git diff main...HEAD`), the draft PR title and description (`pr_draft.md`), and test evidence (`test_evidence.md`), all read against the requirements of the repository and the issue it addresses.

## Inputs and modes

Determine your mode based on invocation:
- **Live mode:** Read inputs from the workspace. Name and collect:
  1. Your issue and its thread (fetched via URL or provided context; or the house-chain issue/repro pack/plan if using the house chain).
  2. Your implementation plan (`plan.md` including any deviation notes).
  3. Your branch's diff, produced by running `git diff main...HEAD` from the working copy.
  4. Your draft PR title and description (`pr_draft.md`).
  5. Your test evidence (`test_evidence.md`).
- **Eval mode:** Read inputs strictly from the designated practice submission bundle in `eval/packages/`. Treat the bundle as the entire world; fetch nothing from outside, assume local files contain all necessary evidence, and run every check with the full rubric verdict rule.

## The scope seam (live mode only)

In live mode, read `scope.md` at startup. Check the `Repo:` line:
- If the line contains an unfilled placeholder, immediately refuse to grade and instruct the user to update `scope.md` with their Path Review repo name.
- If a valid repository is specified, ensure the target repository matches the scope rules before proceeding.
- Eval mode ignores `scope.md` entirely.

## The voice seam (live mode only)

In live mode, read `voice-guide.md` and use it exclusively to gate-check outgoing text in the draft PR title and description (`pr_draft.md`). Report any broken voice or tone rules as feedback, but remember that voice-guide violations never change the final binary verdict (`accept` or `reject`) on their own. Eval mode ignores `voice-guide.md` entirely.

## Component reads

Connect the system components strictly as follows:
- Read `rubric.md` to establish the active checks and the verdict rule.
- Read `references/evidence-guide.md` to map where each evidence family resides.
- Execute `procedure.md` step-by-step as written.
- If `procedure.md` is silent on a step, report the gap explicitly; never improvise around it.
- If `rubric.md` or `procedure.md` contains no content or is missing, trigger the refusal rule immediately and halt execution.

## Verdict and output

Operate within a binary verdict space where `accept` means ready to submit and `reject` means hold. End your entire response with the exact fenced JSON block below, valid and last, with nothing after it. Do not alter the schema.

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

## Grading discipline

Operate under these standing rules:
- **Evidence first:** Always anchor every grade and claim to specific text or diff evidence before assigning a pass, fail, or unclear mark.
- **Grade the thing, not the polish:** Evaluate substantive correctness, test coverage, and alignment with the plan rather than superficial styling.
- **The rubric decides:** Let the rules and weights defined in `rubric.md` dictate the outcome.
- **The procedure decides how:** Follow the exact sequence prescribed in `procedure.md`.
- **Handle unclear grades strictly:** When the rubric's verdict rule is silent on how to treat an `unclear` grade, default to treating it conservatively as a failure condition or holding the PR.