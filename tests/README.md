# Testing the claude-code-gtm-operator-workflow

Each test file contains:

1. a test prompt
2. a validation checklist
3. failure indicators

## How to Run

1. Load the relevant skill file in Claude Code.
2. Run the test prompt exactly as written.
3. Validate output against the checklist.
4. Treat any failure indicator as a failed test.

## Test Files

| File | Skill it tests |
|------|---------------|
| `test-remote-operator-setup.md` | remote-operator-setup |
| `test-parallel-session-orchestrator.md` | parallel-session-orchestrator |
| `test-safe-permissions-policy.md` | safe-permissions-policy |
| `test-mcp-integration-patterns.md` | mcp-integration-patterns |
| `test-verification-loop-enforcer.md` | verification-loop-enforcer |
| `test-gtm-strategy-foundation-prompt.md` | gtm-strategy-foundation-prompt |
