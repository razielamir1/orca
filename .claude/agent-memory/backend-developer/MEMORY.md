# Backend Developer Memory

This file tracks API patterns, middleware conventions, and architectural decisions.

## API Patterns
<!-- Add endpoint conventions and patterns here -->

## Middleware
<!-- Add reusable middleware and their purpose here -->

## Architecture Decisions
- Agent Handoff Protocol added to CLAUDE.md (2026-03-23): completing agents must emit a structured handoff summary (files changed, decisions, next-agent context, open questions) before the next agent begins.
- /new-feature command updated (2026-03-23): architect now analyzes feature scope and selects only the relevant agents rather than always running the full pipeline. Routing rules are explicit in the command file. User must type PROCEED after seeing the recommended pipeline.
- Agent files made stack-adaptive (2026-03-23): frontend-developer.md, ui-designer.md, backend-developer.md, database-expert.md, and qa-expert.md were updated. Each now reads CLAUDE.md at startup and adapts to the project's actual Tech Stack. React/TypeScript/Express/PostgreSQL/TailwindCSS remain as default fallbacks. The qa-expert also now detects the test runner via config file presence rather than assuming `npm test`.
