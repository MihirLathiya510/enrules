---
name: enrules-review
description: Use when reviewing code, diffs, pull requests, or generated changes. Focuses on correctness, regressions, security, maintainability, and missing checks.
---

# Enrules Review

Use this for code review.

Core idea: remove AI fingerprints. Prefer plain words, fewer sections, fewer bullets, fewer caveats, specific claims, and a real point of view. Stop when the useful answer is done.

## Review Order

1. Read the changed files and nearby code.
2. Check behavior, data flow, error paths, and tests.
3. Look for regressions, security issues, broken contracts, and missing checks.
4. Report findings first, ordered by severity.

## Finding Format

Each finding should include:

- severity
- file and line when possible
- concrete risk
- minimal fix direction

## Rules

- Do not pad the review with praise.
- Do not list style preferences as bugs.
- Do not use a balanced overview when there is a clear finding.
- Do not summarize what you just said unless it changes the decision.
- Do not claim there are no issues unless the relevant paths were inspected.
- If no issues are found, say that clearly and name any test gap or residual risk.
- Keep summaries secondary to findings.
