Run a full audit on the codebase. Launch the following 4 agents IN PARALLEL:

1. `@qa-expert` — scan all source code for bugs, missing tests, and code quality issues. Write findings to `.claude/audits/AUDIT_QA.md`.
2. `@security-analyst` — scan for security vulnerabilities (OWASP Top 10, hardcoded secrets, injection risks). Write findings to `.claude/audits/AUDIT_SECURITY.md`.
3. `@code-reviewer` — review code for best practices, code smells, and maintainability. Write findings to `.claude/audits/AUDIT_CODE_REVIEW.md`.
4. `@performance-optimizer` — profile for performance bottlenecks, N+1 queries, bundle size issues. Write findings to `.claude/audits/AUDIT_PERFORMANCE.md`.

After ALL agents have completed, use `@architect` to read all 4 audit reports and produce a unified, prioritized action plan in `FIXES.md` at the project root. Group by priority (critical → high → medium → low) and assign each fix to the appropriate agent.

Do NOT start implementing any fixes. Present the FIXES.md and wait for the user to type PROCEED.
