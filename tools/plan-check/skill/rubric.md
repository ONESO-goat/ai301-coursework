# Rubric: is this plan ready to post and build from?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| diagnosis-grounded | The plan's stated cause read against the repro evidence blocks | Passes if the plan identifies a specific cause for the bug that is consistent with the repro evidence. | required |
| cause-fits-repro | The plan's stated cause read against every step of the repro evidence, including control steps | Passes if every repro step is consistent with the cause and no step rules it out. | required |
| scope-bounded | The plan's scope statement, non-goal declarations, and list of files to touch | Passes if it names each file it will change, says what it won't touch, contains no extra refactors or features, and directly addresses the root cause. | required |
| test-validity | The plan's test plan section read against the repro evidence steps and artifacts | Passes if the proposed test verifies that the reproduced failure is fixed using observable outcomes. | required |
| regression-awareness | The Scope, Changes, and Test plan sections of the plan | Passes if the plan names adjacent behaviors that could break and says how they will be checked. | preferred |

## Verdict rule

Ready (accept) only if every `required` check passes (P). Any `required` check graded F (fail) means hold (reject). Any `required` check graded ? (unclear) means hold (reject), because we cannot verify the fix targets the real bug. `preferred` checks are reported for feedback but never change the verdict.