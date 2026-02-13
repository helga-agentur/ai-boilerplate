# Architecture Basics

## General Rules
- Prefer loosely coupled components / logic.
- Use clear, transparent and documented contracts.
- Ensure high testability.
- Draw very clear boundaries.
- Do One Thing per component / module / class / function (clearly defined responsibilities).
- Keep things as private as possible; expose only what is necessary.
- Always log or display errors – never fail silently or handle errors silently.

## Functions
- Use small and pure functions. Avoid side effects.
- A function contains no more than ca. 60 lines (one page of paper).
- Don't nest functions more than ca. 2 levels deep; extract logic if necessary.

## Simple Solutions
- Among all valid solutions, choose the simplest one.
- Keep business logic in plain, simple, pure functions (for easy testability) or classes.
- Prefer dependency injection over imports (again: for easier testability).
