Run a focused security audit on the codebase.

1. `@security-analyst` — Perform a comprehensive security scan:
   - Check dependencies with `npm audit`
   - Scan for OWASP Top 10 vulnerabilities
   - Look for hardcoded secrets, API keys, and credentials
   - Review authentication and authorization logic
   - Check CORS, CSP, and security headers
   - Write full report to `.claude/audits/AUDIT_SECURITY.md`

2. Present a brief summary of findings in the conversation, categorized by severity (critical/high/medium/low).

Do NOT fix anything. Report only.
