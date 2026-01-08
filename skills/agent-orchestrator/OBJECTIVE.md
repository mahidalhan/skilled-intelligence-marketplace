# Agent Orchestrator - Objective Document

## Overview

Build an orchestrator skill for Claude Code that coordinates multi-agent task execution using the "Ralph Wiggum Loop" pattern with structured planning phases.

## Core Concepts

### Ralph Wiggum Loop
A pattern (from Vercel AI SDK) where agents execute in a loop, handling tasks iteratively until completion with human checkpoints.

### Planning Mode
Structured back-and-forth between user ↔ orchestrator (and orchestrator ↔ subagents) to create refined execution plans before any code is written.

### AskUserQuestion Tool
Enables subagents to consult the orchestrator when facing ambiguity during planning. Creates a feedback loop that produces higher-quality plans.

## User Flows

### Flow 1: Collaborative Planning → Execution
```
User gives task
    ↓
Orchestrator enters PLAN MODE
    ↓
User ↔ Orchestrator: Back-and-forth refinement
    ↓
Plan approved by user
    ↓
RALPH MODE: Execute plan (loop until complete)
    ↓
Review & human merge
```

### Flow 2: Autonomous Spec Planning → Execution
```
User gives high-level spec
    ↓
Orchestrator plans autonomously (with internal AskUserQuestion loops between orchestrator ↔ subagents)
    ↓
"Ultra Spec Plan" presented for human review
    ↓
User approves/modifies
    ↓
RALPH MODE: Execute
    ↓
Review & merge
```

### Flow 3: Direct Execution (Skip Planning)
```
User gives well-defined task
    ↓
RALPH MODE: Execute directly
    ↓
Review & merge
```

## Key Capabilities

| Capability | Description |
|------------|-------------|
| **Plan Mode** | Interactive planning with user or autonomous with subagents |
| **AskUserQuestion Bridge** | Subagents query orchestrator for clarification during planning |
| **Ralph Wiggum Execution** | Iterative task loop with checkpoints |
| **Review Gate** | Human approval before merge |
| **Mode Selection** | User chooses: plan collaboratively, auto-plan, or direct execute |

## Research Needed

1. **Claude Agent SDK** - Planning mode implementation, tool patterns
2. **Vercel AI SDK** - Ralph Wiggum loop pattern specifics
3. **Existing task-orchestrator skill** - Build on or replace?

## Success Criteria

- [ ] User can interactively plan with orchestrator
- [ ] Orchestrator can use subagents with AskUserQuestion for autonomous planning
- [ ] Execution follows Ralph Wiggum loop pattern
- [ ] Human review gate before merge
- [ ] User can choose planning depth (collaborative, auto, skip)

## Open Questions

1. Should this extend or replace the existing `task-orchestrator` skill?
2. How do subagents invoke AskUserQuestion back to orchestrator (not to human)?
3. What's the checkpoint/save mechanism between Ralph loop iterations?

---

**Status:** Awaiting approval to proceed with research and architecture
