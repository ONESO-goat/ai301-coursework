# Evidence guide: where evidence lives in a plan package

## Diagnosis and grounding

- **Where it lives:** 
  - *Eval mode:* In the candidate plan's diagnosis section (`plan.md`) and the package's `repro-evidence` or issue context block.
  - *Live mode:* In the draft plan (`plan.md`) under the diagnosis/cause heading, cross-referenced against the student's posted reproduction comment and issue description on GitHub.
- **What good looks like:** The stated cause explicitly cites specific behaviors, error logs, or file lines that the repro evidence actually demonstrates. It grounds the failure in observable facts rather than speculation or vague summaries.

## Scope

- **Where it lives:** 
  - *Eval mode:* In the candidate plan's scope statement, non-goal declarations, and the list of files to touch (`plan.md`).
  - *Live mode:* In the draft plan's scope section and file checklist, compared against the issue requirements.
- **What good looks like:** The plan clearly defines a single bounded change that directly addresses the root cause while explicitly listing what is *not* in scope, avoiding any unrelated refactoring or drive-by rewrites.

## Executability

- **Where it lives:** 
  - *Eval mode:* In the approach, file list, and step-by-step implementation notes of the candidate plan (`plan.md`).
  - *Live mode:* In the draft plan's approach and workflow sections, evaluated against the target repository's current structure.
- **What good looks like:** The approach names specific files, functions, or patterns to change in a logical order, providing enough granular detail that a developer could start working immediately without guessing or asking clarifying questions.

## Test plan

- **Where it lives:** 
  - *Eval mode:* In the test plan section of the candidate plan (`plan.md`), compared against the expected output blocks in the repro evidence.
- *Live mode:* In the draft plan's test plan section, checked against the local commands and expected outputs generated during reproduction.
- **What good looks like:** The test plan outlines concrete commands, steps, or checks paired with explicit expected outcomes that directly map back to the repro evidence's artifacts of failure and success.

## Honesty

- **Where it lives:** 
  - *Eval mode:* In the risks, unknowns, and `## Deviations` sections of the candidate plan (`plan.md`).
  - *Live mode:* In the draft plan's risk assessment and post-build deviation logs.
- **What good looks like:** The plan acknowledges realistic edge cases, technical uncertainties, or missing context instead of displaying false confidence, and accurately records any mid-build changes under the deviations heading.

## Comms

- **Where it lives:** 
  - *Eval mode:* In the drafted plan comment (`comment.md`) and the package's repo-facts block (maintainer preferences, contributing asks, AI policies).
  - *Live mode:* In the draft plan comment on GitHub, read directly against the issue's live thread history and repository contribution guidelines.
- **What good looks like:** The comment addresses specific maintainer signals, aligns with repository conventions, and includes required disclosures rather than reading as generic boilerplate.