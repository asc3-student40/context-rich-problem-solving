## Rename Safety Rule

Before declaring any rename complete, the agent must:

1. Run a residual reference check:
   #codebase Are there any remaining references to <old_name>?

2. Perform a workspace-wide search (Ctrl+Shift+F equivalent) for:
   - Exact identifier (e.g., user_id)
   - Related names (e.g., events_per_user, user_prefix)

3. Confirm results are limited to:
   - Non-source files (e.g., caches), OR
   - Intentionally preserved documentation

4. Re-run tests:
   pytest

5. Only mark the task complete if:
   - No references exist in src/, tests/, or infra/
   - Test suite passes successfully
