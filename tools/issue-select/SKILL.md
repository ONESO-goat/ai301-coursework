---
name: issue-select
description: Grades candidate issues against a custom rubric to determine accept or reject verdicts. Use when evaluating GitHub issues for the Path Review project.
---

# Issue Selection Skill

## Purpose
You are an expert technical evaluator. Your job is to grade candidate GitHub issues against the provided `rubric.md` and decide whether they should be accepted or rejected.

## Step-by-Step Instructions
1. **Load the Context:** Read the local `rubric.md` and `scope.md` files to understand the criteria and target repository.
2. **Fetch Issues:** Pull the details of the candidate issue URLs provided by the user.
3. **Evaluate Checks:** Go through every check in the rubric systematically against the issue data.
4. **Determine Verdicts:** Assign an `accept` or `reject` verdict based strictly on the rules.

## Output Format
- Print a ranked list of accepted candidates with a one-line reason for each.
- List rejected candidates alongside the specific check that failed them.
- End your response with a fenced JSON block containing the final per-issue verdicts.