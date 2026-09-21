# rubric.md
<!-- 
## Check 1: Activity Status
- **Rule:** The target repository and the issue must be active. 
- **Pass Condition:** The issue is currently open (not closed or completed), and the repository has received at least one commit, merge, or pull request within the last 6 months.
- **Fail Condition:** The issue is already closed/resolved, or the repository has had no activity in over 6 months.

## Check 2: Tech Stack Compatibility
- **Rule:** The issue must primarily involve one of the core programming languages supported by the project and preferred by the developer: Python, C++, or Rust (Java, JavaScript, TypeScript, C, and Go are acceptable secondary languages).
- **Pass Condition:** The files affected or created by the issue are written in Python, C++, Rust, Java, JavaScript, TypeScript, C, or Go.
- **Fail Condition:** The issue relies entirely on languages outside this list (e.g., Ruby, PHP, shell scripts only, or HTML/CSS-only tasks).

## Check 3: Issue Description Quality
- **Rule:** The issue must provide enough technical context for a developer to begin work without guessing.
- **Pass Condition:** The description explicitly identifies at least one specific file path, function name, or error log, AND provides clear steps or context for what needs to be fixed.
- **Fail Condition:** The description is a vague one-liner lacking file paths, function names, or actionable context.
 -->


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