# sjozsef-skills

Agent skills I use across harnesses (Claude Code, pi).

They are inspired by and mostly taken from [Matt Pocock's skills](https://github.com/mattpocock/skills). Each skill keeps the original text as closely as possible and changes only what was needed to drop dependencies on other skills (setup, issue tracker, triage labels, `tdd`, `code-review`, glossary/ADRs) or to fit my own workflow.

## Skills

| Skill | Based on | Changes from the original |
|---|---|---|
| `grill-me` | `grill-me` / `grilling` | One question at a time instead of rounds. States the goal: move every decision out of the implementation phase. |
| `to-spec` | `to-spec` | Saves the spec to `.scratch/tasks/<task-slug>/spec.md` instead of an issue tracker. |
| `to-tickets` | `to-tickets` | Writes one file per ticket to `.scratch/tasks/<task-slug>/tickets/<NN>-<slug>.md`. No tracker, no status labels. |
| `implement` | `implement` | No `tdd`, no automatic `code-review`, no commit. Adds a rule not to widen the scope. |
| `handoff` | `handoff` | None, taken verbatim. |

## Task files

`to-spec` and `to-tickets` work on a task folder under `.scratch/tasks/<task-slug>/`:

- `spec.md`: the spec
- `tickets/<NN>-<slug>.md`: one sub-task each, sized for a single agent session

Pass the task slug (or a spec path) when invoking a skill; if none is given, the skill makes one up.

## Install

Copy the skill folders into the harness's global skills directory, e.g. for Claude Code:

```sh
cp -r grill-me to-spec to-tickets implement handoff ~/.claude/skills/
```
