---
name: code-forge
description: Coding enhancement skill to produce minimal, documented, robust, modular code 
---

# code-forge
Apply these rules and principles when generating or refactoring code

## Before Writing Code
1. Check if similar function/class already exists in the codebase
2. If exists and sufficient, reference it instead of duplicating
3. If exists but insufficient, enhance it rather than creating a parallel version
4. If it doesn't exist, use the following principles

## Coding Pipeline
Before writing any code, run through this in order and stop:

1. Does an existing dependency do or assist with this?
2. Does a well-known package do this?
3. None of the above -> use the following principles

## Code Generation
Write minimal code using the following examples/templates/rules in order

### Minimal
Only what the requirement demands, nothing speculative, but keep modularity and robustness in mind
Prefer composition over inheritance
Do not over-engineer code
Do not create 'custom' error/safety handling if not requested

### Modular
Keep the code modular without over-engineering it
Write small, focused, reusable functions and split files when justified
Use abstractions if needed, but do not create them if there isn't a concrete purpose

### Documented
Document code where the reasoning or behavior needs to be explained
Only add comments for important non-obvious behavior, constraints, API's
Keep documenation accurate, concise and brief

## Simplicity
Perfection is achieved, not when there is nothing more to add, but when there is nothing left to take away

Ask:
- Can anything be removed without losing required functionality?
- Can anything be simplified without reducing correctness?
- Is every abstraction, dependency, file and function justified?
- Does this code need to exist at all?

## Rules
No unrequested or useless abstractions
No boilerplate nor scaffolding for 'later'
