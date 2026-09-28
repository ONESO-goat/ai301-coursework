
# Evidence guide: where proof lives in a reproduction package

## Environment

* **Where it lives:** In evaluation packages, look under the repo-facts block and the environment section of the reproduction report. In live mode, look in the student's draft report or GitHub comment under the system/environment setup heading.
* **What good looks like:** The versions of dependencies, operating systems, and runtimes explicitly match what the issue target specifies, or any intentional deviations (such as a newer patch version) are explicitly called out and justified.

## Steps

* **Where it lives:** In evaluation packages, look inside the reproduction report's step-by-step instructions or command sequence. In live mode, look in the reproduction steps section of the draft report.
* **What good looks like:** The steps provide a clear starting state (e.g., specific commit hash or branch) and sequential commands that a stranger can copy and execute without missing prerequisite configuration.

## Behavior shown

* **Where it lives:** In evaluation packages, look in the output logs, stack traces, or observed behavior blocks of the reproduction report. In live mode, look in the output/logs section of the draft report or attached comment excerpts.
* **What good looks like:** The included artifact features explicit error messages, stack traces, or exit codes that directly demonstrate the specific bug described in the issue, rather than a generic warning or an unrelated failure.

## Honesty

* **Where it lives:** In evaluation packages, look at the final conclusion section of the report compared against the preceding logs and environment notes. In live mode, look at the alignment between the reported outcome (successful reproduction or honest cannot-reproduce) and the actual command outputs provided.
* **What good looks like:** The report states only what the logs objectively prove—including an honest statement of inability to reproduce if the behavior does not manifest—without fabricating success or overclaiming root cause.

## Comms

* **Where it lives:** In evaluation packages, look in the claim comment and the repo-facts policy checklist. In live mode, look at the posted GitHub claim comment and the repository's contributing guidelines or disclosure policies.
* **What good looks like:** The claim names the specific issue and outlines next steps without promising timelines or fixes, and complies fully with any repo-specific policies (such as mandatory AI-use disclosures).