---
name: code-forge
description: Coding enhancement skill to produce minimal, documented, robust, modular code 
---

# code-forge
Apply these rules and principles when generating or refactoring code.

## Before Writing Code
1. Check if a similar function, class, utility, or abstraction already exists in the codebase.
2. If it exists and is sufficient, reuse it instead of duplicating it.
3. If it exists but is insufficient, consider enhancing it rather than creating a parallel version.
4. Use the findings from this check to inform the implementation.

**Always continue to Code Generation after this check.**

## Coding Pipeline
Before writing code, run through these in order:

1. Does an existing dependency do or assist with this?
2. Does a well-known package do this?
3. If neither is appropriate, use the following principles.

## Code Generation
Write minimal code using the following principles.

### Minimal
Only what the requirement demands, nothing speculative, but keep modularity and robustness in mind.
Prefer composition over inheritance.
Do not over-engineer code.
Do not create custom error or safety handling unless it is necessary for correctness or explicitly requested.
Never write any dead code.

### Modular
Keep the code modular without over-engineering it.
Write small, focused, reusable functions and split files when justified.
Use abstractions if needed, but do not create them if there isn't a concrete purpose.

### Documented
Document code where the reasoning or behavior needs to be explained.
Only add comments for important non-obvious behavior, constraints, and APIs.
Keep documentation accurate, concise, and brief.

## Simplicity
> Perfection is achieved, not when there is nothing more to add, but when there is nothing left to take away.

Ask:
- Can anything be removed without losing required functionality?
- Can anything be simplified without reducing correctness?
- Is every abstraction, file, and function justified?
- Does this code need to exist at all?

## Rules
- No unrequested or useless abstractions.
- No boilerplate or scaffolding for "later".
- Do not duplicate functionality that already exists.
- Do not introduce a new pattern when an existing appropriate pattern can be reused.

## When Refactoring Code
1. Understand what the code does before changing how it does it.
2. Preserve existing behavior, public APIs and contracts unless explicitly told otherwise.
3. Improve one dimension at a time: do not mix refactoring with feature changes, but keep later state in mind.
4. If any dead code exists before generating code, look whether this would be usefull for the new code, if not, remove it.
5. Extract duplicated logic into shared functions.
6. Enhance control flow and fix deep-nesting issues.
7. Do not refactor code if it is not needed.

## Checklist
### Reuse
- [ ] No existing dependency, package, or codebase function covers this
- [ ] No duplicated logic introduced

## Minimal
- [ ] Nothing speculative: no unused parameters, branc hes or abstractions
- [ ] Nothing can be removed without losing required functionality

## Modular
- [ ] Abstractions have a concrete purpose and use
- [ ] Original duplicate logic is shared

## Documented
- [ ] No useless bloated comments exist
- [ ] Documentation is accurate and concise

If any box is unchecked, fix before output.