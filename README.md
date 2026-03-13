# Claude Code GTM Operator Workflow

Operational workflow standards for teams using Claude Code to run GTM engineering
execution across outbound, RevOps, and signal-routing systems. This package
solves the core reliability problem, teams can run many sessions, connect data
tools, and ship outputs fast, but without strict setup, permission policy, and
verification loops, quality drifts and risk rises.

## What's Inside

| File | What it does |
|------|-------------|
| `.claude/skills/remote-operator-setup.md` | Standard setup for stable local and remote Claude Code operation, including reconnect behavior and session limits. |
| `.claude/skills/parallel-session-orchestrator.md` | Runs multi-session execution lanes with role separation, queue control, and handoff rules. |
| `.claude/skills/safe-permissions-policy.md` | Enforces permission mode policy by environment with command allowlists and banned operations. |
| `.claude/skills/mcp-integration-patterns.md` | Defines safe MCP server patterns for GTM systems, including read/write boundaries and audit checks. |
| `.claude/skills/verification-loop-enforcer.md` | Applies deterministic verification loops before output handoff to sales or RevOps operators. |
| `.claude/skills/gtm-strategy-foundation-prompt.md` | Generates a concrete 90-day GTM foundation plan from a minimum input set. |
| `tests/` | Prompt-based tests and checklists for all six skills. |

## Prerequisites

- [ ] Claude Code installed and authenticated
- [ ] Access to the project repository where you will run sessions
- [ ] `.claude/` folder in your project root
- [ ] MCP servers configured for your GTM stack if using the MCP skill
- [ ] Operator with authority to approve sensitive write actions

## Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/forma-norden/claude-code-gtm-operator-workflow.git
   ```
2. Copy the `.claude/skills/` files into your project:
   ```bash
   cp -r claude-code-gtm-operator-workflow/.claude/skills your-project/.claude/
   ```
3. Open your target project in Claude Code and load the required skill before
   execution.

## Usage

Start by loading the setup skill:

```text
Read .claude/skills/remote-operator-setup.md

Context:
- project path: ./gtm-pipeline-core
- environment: staging
- remote check-ins required: yes

Return:
1) startup sequence
2) remote-control sequence
3) failure and recovery path
```

Expected output:

- exact startup command sequence
- safe session limits and monitoring method
- explicit recovery path for dropped remote sessions

## Who This Is For

GTM engineers, RevOps leads, VP Sales, and founders at B2B companies with 50 to 500 employees who are building or consolidating their
outbound infrastructure and want to reduce tool sprawl through
better-engineered GTM systems.

---

---

## From the Forma NÃ´rden GTM Library

This is a free resource from the Forma NÃ´rden open-source GTM library, built by 
[Yananai A. Chiwuta](https://yananaichiwuta.com/), GTM engineer and founder of 
[Forma NÃ´rden](https://formanorden.com/).

- [Open-source GTM systems](https://github.com/forma-norden): all repos in the library  
- [GTM engineering blog](https://formanorden.com/blog/): strategy, systems, and outbound deep-dives  
- [All resources](https://formanorden.com/resources/): guides, frameworks, and templates  

If this saves you time, star the repo and follow 
[Forma NÃ´rden on LinkedIn](https://www.linkedin.com/company/formanorden/).

Built by [Forma NÃ´rden](https://formanorden.com/): GTM engineering for B2B companies.
