---
name: loop-engineering
description: >-
  Supplement iterative work when acceptance coverage is unclear, attempts stall,
  recovery between sessions is needed, or unattended execution is being
  designed. Also use for revising the loop itself. Add evidence mapping,
  progress breakers, recovery notes, and runtime safeguards. Skip routine edits
  and ordinary multi-step tasks.
metadata:
  version: "2.3.1"
---

# Loop Engineering

Use this as a small extension to the agent's normal workflow. For routine work, including routine work explicitly invoking this skill, continue normally without loading the reference or adding loop artifacts.

Read only the relevant section of [references/closed-loop.md](references/closed-loop.md):

- **Acceptance coverage:** connect requirements and failure paths to evidence, distinguish existing failures, and preserve required review and work ownership boundaries.
- **Stalled investigations:** track what repeated attempts establish and break out of an unproductive hypothesis.
- **Recovery between sessions:** preserve the minimum state needed to resume and check whether saved evidence is still valid.
- **Unattended execution:** make duplicate suppression, recovery, budgets, and escalation enforceable by the runner.
- **Changes to the loop:** retain the evidence and evaluation needed to justify a durable workflow change.

There is no minimum cycle count. Successful work needs no additional pass to satisfy this skill.
