
# Rubric: is this reproduction package ready to post?

## Checks

| Check | Evidence | Pass condition | Weight |
| --- | --- | --- | --- |
| env-recorded | The environment section of the reproduction report read against the issue's stated target platform and dependencies. | The operating system, runtime, and dependency versions are explicitly recorded, and any deviations from the issue's target are explicitly called out and justified. | required |
| steps-followable | The step-by-step instructions in the reproduction report read against the starter repository state. | The steps provide a clear starting state and sequential commands that can be executed end-to-end without missing prerequisite setups. | required |
| behavior-matches | The output logs, stack traces, or error codes in the reproduction report read against the original issue description. | The included logs or error artifacts directly demonstrate the exact bug described in the issue, rather than an unrelated warning or adjacent failure. | required |
| outcome-honest | The final conclusion section of the report read against the preceding logs and environment notes. | The conclusion states only what the logs objectively prove—including an evidenced cannot-reproduce statement if the bug did not manifest—without fabricating success or overclaiming root cause. | required |
| claim-specific | The claim comment read against the target GitHub issue. | The claim names the specific issue and outlines next steps without promising fix timelines, delivery dates, or definitive root causes before reproduction. | required |
| disclosure-policy | The claim or repro comments and repo-facts block read against the repository's stated contribution policy and AI-use disclosure requirements. | The submission fully complies with any repo-specific policies, such as explicitly disclosing AI assistance when the repository's policy mandates it. | required |
| style-preferred | The tone and formatting of the draft comments read against general technical clarity standards. | The text avoids conversational filler and keeps descriptions concise and direct. | preferred |

## Verdict rule

Accept if every required check passes. Preferred checks never change the verdict. Any check returning unclear counts as a fail, resulting in a reject verdict.