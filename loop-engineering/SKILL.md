---
name: loop-engineering
description: >-
  Add a no-progress breaker for stalled investigations, recovery notes for
  interrupted work, and runtime safeguards for unattended workflows. Use when
  repeated attempts stop producing evidence, continuity across sessions is
  needed, or unattended execution is being designed. Skip routine edits and
  ordinary multi-step tasks.
metadata:
  version: "2.3.0"
---

# Loop Engineering

Use this as a small extension to the agent's normal workflow. For routine work, including routine work explicitly invoking this skill, continue normally without loading the reference or adding loop artifacts.

Read only the relevant section of [references/closed-loop.md](references/closed-loop.md):

- **Stalled investigations:** track what repeated attempts establish and break out of an unproductive hypothesis.
- **Recovery between sessions:** preserve the minimum state needed to resume and check whether saved evidence is still valid.
- **Unattended execution:** make duplicate suppression, recovery, budgets, and escalation enforceable by the runner.

There is no minimum cycle count. Successful work needs no additional pass to satisfy this skill.
