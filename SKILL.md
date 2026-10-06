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