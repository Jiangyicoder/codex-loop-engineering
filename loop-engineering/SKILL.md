---
name: loop-engineering
description: >-
  Guide complex or consequential Codex work through evidence-based iteration,
  including difficult debugging, cross-session tasks, and unattended workflows.
  Also use for loop engineering and autonomous workflow design. Do not activate
  solely because a task has several steps or can be tested. Skip simple answers
  and routine low-risk edits; if explicitly invoked for them, use Direct.
metadata:
  version: "2.2.0"
---

# Codex Bounded Evidence Loop

Move work toward the user's outcome through observable feedback within existing authority and resource limits. Scale the process to the task: extra planning, artifacts, tests, and reviews must justify their cost. No named custom agents are required.

## Reasoning effort and completion

This skill controls the work process, not the model's internal reasoning effort. Preserve the user's selected model and effort, including Astra at `xhigh`, `max`, or an available `ultra` mode. These settings do not prescribe a loop count, broader tests, or additional agents. Do not inspect or change model configuration just to route an ordinary task. Treat available tools and active instructions as authoritative for delegation; an effort label alone is not permission to spawn agents.

Finish as soon as the requested outcome and its required checks are satisfied, even on the first pass. There is no minimum number of iterations. Continue only for unfinished requirements, failed checks, material uncertainty, or explicitly required validation. More available reasoning or budget does not justify repeated verification. Higher reasoning effort also does not replace evidence for consequential changes.

## Route first

Choose the lightest adequate mode by risk, scope, uncertainty, and recovery needs, not by tool-call count, diff size, or reasoning effort. Respect explicit user requirements and applicable project validation rules.

- **Direct:** routine, well-scoped, low-risk work, including a short inspect-edit-check sequence or several independent mechanical edits. Infer the intended result and boundaries internally, do the work, perform the smallest relevant check, and report briefly. Do not add a formal plan, contract checklist, state file, worktree, or review role just to follow this skill. **Do not load the Closed Loop reference for Direct work.**
- **Closed Loop:** work with interacting behavioral changes, difficult debugging, consequential behavior, repeated failed approaches, or recovery/unattended needs. Read [references/closed-loop.md](references/closed-loop.md) and use the relevant sections without turning each into a required artifact. One successful pass is sufficient.
- **Exploration:** the user requests research, review, or options without implementation, or an unresolved outcome, acceptance condition, or major trade-off prevents responsible implementation. Investigate bounded questions and deliver the requested findings. For an implementation request, continue once uncertainty is resolved within existing scope and authority; ask only for unresolved material decisions. A research-only request does not authorize implementation. Load the Closed Loop reference only if the investigation itself needs that procedure.

An unknown implementation path alone is not a reason to stop at a proposal. If the user has authorized a clear outcome, investigate within Direct or Closed Loop and continue through implementation and verification.

A spelling-only correction in prose normally needs inspecting the edited text or diff, not a new test or a full build. A one-character change to authorization logic may need behavioral tests and review. Reassess the mode when evidence changes the consequences.

A failed check with a clear local cause can stay Direct: fix it and rerun the affected check. Escalate to Closed Loop when failure reveals interacting behavior, substantial risk, or unresolved diagnosis; a single failed command does not automatically require the full protocol.

For Direct work, a brief result and relevant check or limitation are sufficient. Once those satisfy the request, stop. Recurring or scheduled work additionally uses the scheduling safeguards in the Closed Loop reference, and creating automation requires a user request.
