# Engineering Standards (Clean Code)

## Core Principles
- **Single Responsibility:** Every module, class, and function must have one clear purpose. Avoid generic "and" names (e.g., `fetchAndParse`).
- **Naming:** Use intention-revealing, searchable names. Avoid cryptic abbreviations and magic numbers; extract constants instead.
- **Small & Focused:** Keep functions short, flat (avoid deep nesting via early returns), and operating at a single level of abstraction.
- **DRY & YAGNI:** Eliminate duplicated logic, but do not build speculative abstractions for future requirements.

## Code Hygiene
- **Comments:** Never write inline comments. Write self-documenting code. Use doc block comments only to explain *why* 
  a 
  non-obvious decision was 
  made, never *what* the code does. Crete new variables that describe their purpose and express the comment.
- **Dead Code:** Delete unused variables, imports, functions, and commented-out blocks immediately.
- **Error Handling:** Fail fast with clear, actionable error messages. Never silently swallow exceptions.

## TypeScript Style & Philosophy
- **Use TypeScript for documentation, not type-level programming.** Types should clarify data shapes and intent for human readers.
- **No typing gymnastics.** Avoid complex conditional types, recursive types, multi-layered generics, `infer` tricks, and intricate mapped types.
- **Keep types flat and concrete.** Prefer explicit interfaces/types and standard union types over dynamically computed or heavily transformed utility types.
- **Lean on inference.** Do not over-annotate internal variables when TypeScript already infers the type cleanly.
- **Prioritize code clarity.** If a type signature becomes harder to read than the runtime JavaScript it describes, simplify the type.


## Workflow & Testing
- **Tests:** Verify behavior and edge cases rather than implementation details. Keep tests fast, deterministic, and independent.
- **Scope:** Make minimal, targeted changes. Refactor adjacent mess only when it directly blocks clean implementation.
- **Verification:** Run the project's test suite and linter before considering any task complete.

## Git & Pull Requests
- **Sync before starting and before every push.** Run `git fetch origin`, then check the current branch's PR state with `gh pr view --json state`.
  - **PR merged or closed:** never push to that branch. Start a new branch from the latest `origin/<default-branch>` and move any unmerged commits onto it.
  - **PR open, or no PR yet:** rebase onto the latest `origin/<default-branch>` before pushing. Merge it in instead if someone else has pushed to the branch.
- **Verify, don't trust notes.** Check PR, branch and deploy state on GitHub rather than relying on handoff docs or earlier conversation, and do it before reporting that state.


