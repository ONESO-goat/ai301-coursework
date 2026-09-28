# rubric.md


# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-active | The issue comment thread and last maintainer activity in the repo-facts block. | A project maintainer has commented, merged, or closed an issue within the last 90 days. | required |
| repo-in-use | The last 5 default-branch commit dates from the repo-facts block. | The repository has received at least one commit within the last 60 days. | required |
| scope-newcomer | The issue body and linked files/directories. | The scope affects 3 files or fewer and includes explicit instructions or error logs. | required |
| unclaimed | The issue comment thread for assignment or active PR links. | No other contributor has been assigned or stated they are working on it within the last 14 days. | required |
| labeled-beginner | The issue labels list in the issue body. | The issue is labeled with "good first issue" or "help wanted". | preferred |

## Verdict rule

Accept if every required check passes; preferred checks never change the verdict, they rank accepted issues; unclear counts as fail.