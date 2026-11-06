
● Skill(issue-scout)
Successfully loaded skill
5 skills available

  Read 4 files, ran 2 shell commands

Strategy and rubric are both filled in. Running the two queries now.

  Ran 3 shell commands

Funnel narrowed 200 results down to 141 recently updated, unassigned items, buwith no tie-break rule, so the top 5 just reflect search order — I'll flag thatas friction. Next I'll gather evidence for those top 5.

  Ran 3 shell commands

● Auto mode lets Claude handle permission prompts automatically — Claude checks each tool call for risky actions and prompt injection before executing. Actions Claude identifies as
  safe are executed, while actions Claude identifies as risky are blocked and Cloach. Ideal for long-running tasks. Sessions are slightly moreexpensive. Claude can make mistakes that allow harmful commands to run, it's recommended to only use in isolated environments. Shift+Tab to change mode.

● Write(~/.claude/skills/issue-scout/scan-notes.md)
Wrote 24 lines to ~/.claude/skills/issue-scout/scan-notes.md
# Scan notes

## 2026-10-28 scan

Funnel: q1 100 + q2 100 → 200 unique → 168 unassigned → 141 updated ≤45d → top 5.

- **No tie-break in ranking.** 113 of 141 survivors tied at 0 comments, so the
  top 5 were decided by search return order, not by the strategy. All 5 cam
  from q1; q2 (JS bugs) never reached grading. Add a tie-break (e.g. most
  recently updated first) or interleave queries.
… +14 lines
Allowed by auto mode classifier

Scan results, 2026-10-28

How the funnel narrowed: the two queries returned 200 unique issues. 168 had nwere updated in the last 45 days. Sorting by fewest comments left 113 issuestied at 0 comments. The strategy has no tie-break, so search return order picked the top 5. All 5 came from q1 (Python CLI, "good first issue"). None of the q2 results (JavaScript bugs)
reached grading.

Accepted, best fit first

1. YakDriver/oschmod#194: "CLI: accept multiple paths"
   - Why it fits: a small Python CLI with pytest, an established repo (6 years old), and a maintainer who merged PRs today. The change is one argparse argument (nargs="+") in
     oschmod/cli.py plus tests/test_cli.py.
   - Before you start: this repo uses vouch. PRs from contributors not listed in .github/VOUCHED.td are closed automatically, so you need to get vouched first (see CONTRIBUTING.md). The
     issue was also opened only about an hour ago.
   - How it got here: q1, no assignee, updated today, 0 comments.
2. bdperkin/findfmt#366: "Validate numeric CLI parameters"
   - Why it fits: a Python click CLI with pytest, and the maintainer merges daily. The issue names its 3 files and has acceptance criteria.
   - Before you start: the repo is 3 weeks old with 2 stars. The issue is a suudit note corrects the original file and flag details, so read the audit beforeplanning.
   - How it got here: q1, no assignee, updated 10-23, 0 comments.
3. Ranjeet2063/aetherguard#34: "Shell auto-completion"
   - Fit is poor: the work is in Rust (clap_complete, Cargo.toml), even thoughthon. It passes the rubric, but it's outside your languages.
   - How it got here: q1, no assignee, updated 10-13, 0 comments.
4. shmindmaster/crewscore#76: "Document CLI exit codes"
   - You can't actually take this one: the rubric accepts it, but the repo is archived. Archived repos are read-only, so no PR can be opened. The rubric has no check for archived repos,
     so I graded it as written and logged the gap.
   - How it got here: q1, no assignee, updated 10-15, 0 comments.

Rejected

- Priyanshu-byte-coder/contextrot#14: "Adapter: Cursor CLI" failed scope-newcomer. The acceptance criteria require 4 files (adapter, __init__, fixture, test), and the issue says the
  transcript format is "not yet verified." It came from q1, no assignee, updat

My pick: oschmod#194, once you're vouched. Per your scope rules, comment on ths you commit. If the vouch step is a blocker, take findfmt#366 instead.

Problems with the strategy and rubric

I wrote these to /home/oneso/.claude/skills/issue-scout/scan-notes.md:
- Strategy: the ranking needs a tie-break (for example, most recently updated first).
- Rubric: repo-in-use should also require that the repo isn't archived.
- Search: --language matches the repo's main language, not the language of the issue's code.
- Rubric: there's no check for the repo's contribution policy, so the vouch re
- Rubric: the "3 files or fewer" rule is hard to apply when an issue names no files.

json
[
  {
    "item": "https://github.com/YakDriver/oschmod/issues/194",
    "checks": [
      {"name": "maintainer-active", "grade": "pass", "evidence": "Owner YakDriclosed #187 on 2026-10-28."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Last default-branch commit 2026-10-28 (today)."},
      {"name": "scope-newcomer", "grade": "pass", "evidence": "Explicit instrument accept one or more paths (nargs=\"+\")' plus the error 'unrecognizedarguments'; the CLI lives in the single oschmod/cli.py with tests/test_cli.py."},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, 0 comm."},
      {"name": "labeled-beginner", "grade": "pass", "evidence": "Labels: enhancement, good first issue."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/bdperkin/findfmt/issues/366",
    "checks": [
      {"name": "maintainer-active", "grade": "pass", "evidence": "Owner bdperk closed #499 on 2026-10-24."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Last commit 2026-10-27."},
      {"name": "scope-newcomer", "grade": "pass", "evidence": "Affected modulein.py; acceptance criteria: '-L -1 ... exits with code 2'."},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments, no PRs referencing #366."},
      {"name": "labeled-beginner", "grade": "pass", "evidence": "Labels includ
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/Ranjeet2063/aetherguard/issues/34",
    "checks": [
      {"name": "maintainer-active", "grade": "pass", "evidence": "Owner Ranjeet2063 merged #56 and closed #43 on 2026-10-21."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Last commit 2026-1
      {"name": "scope-newcomer", "grade": "pass", "evidence": "Three steps: add clap_complete to Cargo.toml, add a completions command, document install."},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, 0 comm"},
      {"name": "labeled-beginner", "grade": "pass", "evidence": "Labels: good first issue, rust, cli."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/shmindmaster/crewscore/issues/76",
    "checks": [
      {"name": "maintainer-active", "grade": "pass", "evidence": "Owner opened2026-10-15."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Last commit 2026-10-15 ('docs: archive notice; superseded by Assay'); repo archived=true, which the check does not test."},
      {"name": "scope-newcomer", "grade": "pass", "evidence": "'Done when' lisd from crewscore/cli.py plus one test in tests/."},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments, no PRs referencing #76."},
      {"name": "labeled-beginner", "grade": "pass", "evidence": "Labels: docum
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/Priyanshu-byte-coder/contextrot/issues/14",
    "checks": [
      {"name": "maintainer-active", "grade": "pass", "evidence": "Owner merged #17 on 2026-10-11."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Last commit 2026-1
      {"name": "scope-newcomer", "grade": "fail", "evidence": "Acceptance needs adapter file, adapters/__init__.py, fixture, and test file (4 files); format 'Not yet verified against a
real transcript'."},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments, no PRs referencing #14."},
      {"name": "labeled-beginner", "grade": "pass", "evidence": "Labels: good
    ],
    "verdict": "reject"
  }
]
