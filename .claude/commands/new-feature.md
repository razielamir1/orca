Plan and implement a new feature using a smart, trimmed agent pipeline.

Follow this sequence:

1. `@prompt-architect` — Refine the raw feature request into a clear, unambiguous specification. Output the refined prompt before continuing.

2. `@architect` — Using the refined specification, analyze what the feature actually requires, then:
   a. Determine which agents are needed from the full list below (skip agents whose domain is not touched by this feature).
   b. Present the recommended pipeline to the user in this format:

   ```
   ### Recommended Pipeline for: <feature name>

   Agents selected:
   - [agent-name] — [one-line reason]
   - ...

   Agents skipped:
   - [agent-name] — [one-line reason why not needed]

   Proceed with this pipeline?
   ```

   c. Wait for the user to type **PROCEED** before any implementation begins.

   Routing rules (apply all that fit):
   - Feature touches database schemas or queries → include `database-expert`
   - Feature adds or modifies API endpoints or server logic → include `backend-developer`
   - Feature has frontend state, routing, or data fetching → include `frontend-developer`
   - Feature has new or changed UI components or styling → include `ui-designer`
   - UI-only feature (no data persistence, no API) → skip `database-expert` and `backend-developer`
   - Backend/API-only feature (no UI) → skip `frontend-developer` and `ui-designer`
   - Database migration with no application-layer changes → skip all frontend agents
   - Always end with `qa-expert` if any code is written.

3. Execute the approved pipeline in order. Each completing agent must produce a handoff summary (see Agent Handoff Protocol in CLAUDE.md) before the next agent begins.

4. `@qa-expert` — Run tests and scan for bugs. Write report to `.claude/audits/AUDIT_QA.md`.

Feature to build: $ARGUMENTS
