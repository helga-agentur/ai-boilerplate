---
description: Generate Implementation Spec from GitHub Issue
argument-hint: <issue-number>
---
# Analyze Issue #$ARGUMENTS

In General
===
- Keep it short and clean.
- Resolve contradictions; if unsure, ask for clarification.
- Don't repeat yourself.
- Suppress everything obvious; people working on it are smart and competent.
- Don't go into implementation details yet.
- Focus. Limit yourself to 200 lines max.

Tasks
===
1. Fetch issue: `gh issue view $ARGUMENTS`
2. **Requirements Analysis**
   - Extract user story and acceptance criteria
   - List functional requirements
   - Note non-functional requirements (performance, security, …)
3. **Test Strategy**
   - List manual test scenarios
   - Define edge cases to cover
4. **External Review**
   - As a skilled, neutral business analyst, look over the spec you wrote.
   - Find all ambiguities, contradictions and topics that need clarification.
   - Ask for clarification if needed. Fix them.
5. **Manual Review**
   - Let me look over the spec.
   - Wait until all my input has been implemented and I tell you to proceed.

Create `specs/issue-$ARGUMENTS-spec.md` with complete analysis.
