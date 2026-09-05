# Loop-specific procedures

## Acceptance coverage

Before prolonged or consequential iteration, map requirements and key failure paths to checks with expected outcomes. A passing check does not establish coverage of a requirement it never exercises. Keep this mapping concise; a separate contract document is optional.

For a reproducible bug, prefer evidence that fails before the fix and passes after it when feasible. Identify pre-existing failures so that they remain distinguishable from new regressions.

Keep acceptance stable across attempts. Correct the mapping when requirements or assumptions change; do not weaken a gate merely to obtain a pass. Treat an explicitly required independent review as a separate gate that self-review cannot satisfy.

When implementations write concurrently, use separate checkouts and explicit ownership boundaries.

## Stalled investigations

When attempts start repeating, keep a short evidence ledger:

```text
Hypothesis | action that can distinguish it | observation | consequence for the next attempt
```

Two consecutive attempts testing the same hypothesis with the same failure and no new evidence trigger a strategy change. If no useful alternative exists for that line of attack, retire it and report the remaining blocker. Count hypothesis attempts, not tool calls; this limits a dead end, not the whole task.

Another log is not progress unless it changes the diagnosis, narrows the possibilities, or changes the next action.

For open-ended interactive investigation, set a finite checkpoint for the current hypothesis or phase. Reassess at that checkpoint rather than silently imposing a whole-task cutoff.

## Recovery between sessions

When interruption or a later session would otherwise lose important working state, use the project's existing tracker or a compact task note in a writable workspace location. Update it at meaningful checkpoints rather than after each tool call:

```text
Outcome / outstanding requirements:
Workspace: repository, branch, commit, uncommitted changes
Baseline: known pre-existing failures
Evidence: check, observed result, artifact revision, relevant inputs/environment
Attempts: hypothesis, observation, resulting decision
Next action / blockers:
Remaining limits / authorized operations:
```

On resume, reconcile the note with the current request and live workspace before continuing. Reuse saved evidence only while its artifact, inputs, and relevant environment still match; a saved passed marker alone is insufficient.

## Unattended execution

An unattended runner needs implemented mechanisms for:

- A trigger and an observation that distinguish actionable work, confirmed unchanged state, and observation failure.
- Durable action records and idempotency keys to suppress duplicate execution. After interruption, reconcile the recorded action with the actual result before replaying it.
- A lock against concurrent writes to the same target; isolate unattended repository writes from active checkouts.
- Enforced per-run and cumulative limits that survive restarts.
- Machine-checkable success and stop conditions, plus an escalation destination.
- The exact allowed operations and write targets for the run.

Confirmed unchanged state ends the run without mutation. A failed observation is an error or unknown state, not evidence that nothing changed.

If the runner cannot enforce the required controls, keep execution supervised. Written requirements alone do not implement these safeguards.

## Changes to the loop

Outside a user-requested revision, propose a durable workflow change only after repeated failures or one high-severity incident. Retain the triggering evidence, affected rule, smallest proposed change, relevant before/after evaluation, and a rollback or retirement condition. Preserve negative results so that apparent improvements can be checked against earlier misses or regressions.
