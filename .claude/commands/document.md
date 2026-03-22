Generate or update project documentation.

Use `@tech-writer` to:
1. Read the codebase thoroughly — understand all modules, endpoints, components, and utilities.
2. Generate the requested documentation type based on the arguments:
   - If "api" → Generate API reference documentation for all endpoints
   - If "readme" → Generate or update the project README
   - If "onboarding" → Generate a developer onboarding guide
   - If "jsdoc" → Add JSDoc/TSDoc comments to all exported functions
   - If no argument → Generate a comprehensive documentation set (API + README + onboarding)

Documentation request: $ARGUMENTS
