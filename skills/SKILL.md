---
name: skills
description: "Mandatory coding skill. Invoke BEFORE: writing code, refactoring code, creating a new project, adding a dependency, reading or analyzing code. Produces minimal, documented, robust, modular code. Always active for any coding task."
---

# skills
Apply these rules and principles when generating or refactoring code.

## Activation
This skill is always active. Load these rules before any coding task.
If you are about to write, refactor, analyze, or review code, apply these rules first.

## Overall Pipeline
All sections always apply, but use the correct order based on your task and the Overall Pipeline Rules. 

### Overall Pipeline Rules
- Every section applies unless explicitly irrelevant to the task.
- Apply sections in whatever order makes sense for the task.
- Sections can be brought forth multiple times in an order.
- Checklist is last, and always mandatory.

## Adding a dependency
When adding a dependency.

### How To Add
Add a dependency using the supported command if possible, only change direct file if needed. 

For instance:

`cargo add {dependency}`

`bun add {dependency}`

## Creating a project
When creating a new project, following the Architecture section.

### Templates
Use existing minimal templates/cli commands to setup the base project, rather then creating files manually.

For instance:

`cargo new {project_name}`

`bun create astro {project_name}`

## Code Analysis
Use this when analysing, reviewing or reading code.

### What To Check
Run through these in order, report findings, do not do unnecessary changes, output in Analysis Output Format:

#### Correctness
- Does the code do what it claims / is supposed to do?
- Are there logic errors, off-by-one errors, or unhandled edge cases?
- Are there race conditions or state issues?

#### Simplicity Violations
- Dead code (unused variables, functions, imports, branches)
- Over-abstraction (single-use abstractions, unnecessary indirection)
- Duplicate logic that should be shared.
- Speculative code (parameters/branches never used)

#### Structure Issues
- Functions doing things that it shouldn't do.
- Deep nesting with bad returns.
- Missing seperation of concerns.
- Circular or tangled dependencies.

#### Documentation Gaps
- Missing really needed documentation.
- Misleading or outdated comments.

### Analysis Output Format
Severity: [Critical | Warning | Info]
Location: file, line, or function name
Issue: What is wrong
Suggestion: How to fix (one line) 

## Before Writing Code
1. Check if a similar function, class, utility, or abstraction already exists in the codebase.
2. If it exists and is sufficient, reuse it instead of duplicating it.
3. If it exists but is insufficient, consider enhancing it rather than creating a parallel version.
4. Use the findings from this check to inform the implementation.

## Architecture
When deciding file structure, module organization or project layout.

### Principles
- Start with the base simplest structure that works.
- Split files when they become hard to navigate.
- Group by feature/domain, and in the correct situation use technical types.
- Nest if needed, but avoid deep nesting.

### When To Create A New File/Module
- The logic has a distinct responsibility unrelated to existing files.
- The file would otherwise mix multiple concerns.
- The module will be reused from multiple places.
- Do NOT create a file for future.

### When NOT To Abstract
- Only one implementation exists and no second is planned.
- The abstraction saves fewer lines than it adds in indirection.
- The abstraction exists to 'make things cleaner' without concrete benefit.

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

## Simplicity
- [ ] It follows the 'Perfection is achieved, not when there is nothing more to add, but when there is nothing left to take away.' rule.

If any box is unchecked, fix before output.