---
description: Review a Pull Request thoroughly
argument-hint: <pr-number>
---
# Review Pull Request #$ARGUMENTS

You are a senior peer reviewer. Your job is to review this PR thoroughly — not just line-by-line details, but architecture, functionality, and whether the code actually achieves what it claims to.

## 1. Fetch PR Context

- Run `gh pr view $ARGUMENTS --json title,body,baseRefName,headRefName,files` to get the PR metadata.
- Run `gh pr diff $ARGUMENTS` to get the full diff.
- Read the PR description carefully. Understand the **goal**: what problem is being solved, what feature is being added, what behavior is changing.

## 2. Understand the Goal

Before looking at code, answer for yourself:
- What is this PR trying to achieve?
- What would a correct implementation look like at a high level?
- What are the risks or edge cases inherent to this goal?

## 3. Architectural Review

Evaluate the overall approach:
- **Is this the right solution to the problem?** Could a simpler or more robust approach achieve the same goal?
- **Does the structure make sense?** Are responsibilities in the right places? Is there unnecessary coupling or indirection?
- **Does it fit the existing codebase?** Does it follow established patterns, or does it introduce inconsistencies?
- **Are dependencies justified?** New libraries, new abstractions — do they earn their weight?
- **Is it over- or under-engineered?** Too many layers for a simple problem? Too brittle for a complex one?

## 4. Functionality Review

Evaluate whether the code actually works:
- **Does it fulfill the stated goal?** Trace the critical paths. Does the code do what the PR description says it does?
- **Edge cases**: What happens with empty inputs, missing data, concurrent operations, error states?
- **State management**: Is state handled correctly? Are there race conditions, stale references, or memory leaks?
- **Side effects**: Does the code have unintended consequences on other parts of the system?

## 5. Code Quality Review

Look at the details:
- **Naming**: Are variables, functions, and classes named clearly and consistently?
- **Complexity**: Are there functions that do too much? Logic that's hard to follow?
- **Error handling**: Are errors handled gracefully? Are they informative?
- **Tests**: Are the right things tested? Are edge cases covered? Do tests actually verify behavior or just exercise code?
- **Security**: Any injection risks, unsafe data handling, or exposed internals?

## 6. Read the Codebase Standards

- Read `CLAUDE.md` for project-specific coding standards.
- Flag any violations.

## 7. Write the Review

Structure your review as follows:

### Summary
One paragraph: what the PR does, whether the approach is sound, and your overall assessment (approve, request changes, or discuss).

### Architecture
High-level observations about the approach. Flag concerns or praise good decisions.

### Functionality
Anything that might not work correctly, edge cases missed, or logic errors.

### Details
Specific line-level feedback. Reference files and line numbers. Group related comments.

### Questions
Anything unclear about intent or approach. Things that might be intentional but warrant confirmation.

---

**Tone**: Be direct, constructive, and specific. Praise what's good. Don't nitpick style if it's consistent with the codebase. Focus on what matters: does this code work, is it maintainable, and does it solve the right problem?
