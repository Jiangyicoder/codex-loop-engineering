# Loop-specific procedures

## Stalled investigations

When attempts start repeating, keep a short evidence ledger:

```text
Hypothesis | action that can distinguish it | observation | consequence for the next attempt
```

Two consecutive attempts testing the same hypothesis with the same failure and no new evidence trigger a strategy change. If no useful alternative exists for that line of attack, retire it and report the remaining blocker. Count hypothesis attempts, not tool calls; this limits a dead end, not the whole task.

Another log is not progress unless it changes the diagnosis, narrows the possibilities, or changes the next action.

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
