
# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`
command: python3 run_eval.py --rubric codepath/AI301/rubric.md --save-run eval-run.txt

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

Link: https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72

**Verdict output**

Grading candidate: [https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72](https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72)
- maintainer-active: PASS (maintainer commented 4 days ago)
- repo-in-use: PASS (commit made yesterday)
- scope-newcomer: PASS (affects 2 files, clear instructions provided)
- unclaimed: PASS (no assignee or active PR)
- labeled-beginner: PASS (labeled 'good first issue')

```json
{
  "[https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72](https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72)": {
    "verdict": "accept",
    "reason": "Meets all required checks: active maintainer, active repo, manageable scope, and unclaimed."
  }
}
```
## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

Run 1: 17/20 (missed category floor on documentation); Run 2: 19/20 (final run committed in eval-run.txt).

---

## Issue analysis

issue-03: My rubric decided to accept this issue because it had an open status and a clear error log in the description. However, the gold label was reject because the issue was actually superseded by an open pull request. My rubric failed to check for active PR links in the comment thread, leading to a false positive which I later adjusted for.

---

## Check rationale

**scope-newcomer:** "The issue body and linked files/directories. Pass condition: The scope affects 3 files or fewer and includes explicit instructions or error logs. Weight: required."
Reasoning: Written this strict form to ensure newcomers do not get bogged down in massive refactors or multi-module architectures where they can't easily isolate the bug.

---

## Trade-offs

The scope-newcomer check gives up large structural bug fixes that might only touch one file conceptually but require deep context across abstract base classes. I accept that it will miss these deeper architectural issues to protect newcomers from rabbit holes.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length, but on a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

**Fit to interests and time:** This issue involves a clean bug fix in a Python utility module that matches my interest in backend tooling, and I have a solid window of availability this week to tackle it.

**Verdict accuracy and extra weight:** The verdict correctly pinpointed that the affected files are isolated and well-documented. Beyond the rubric criteria, I noticed the specific error message matches a traceback I've successfully debugged before, giving me extra confidence.

**Anticipated difficulty:** Since it is a popular introductory repository, competition to claim it first might be tight, so I need to ensure my voice guide and claim comment are sharp and ready for Unit 2.

**Related paths:** eval-run.txt in this directory; your skill's files in
tools/issue-select/.
