# Guardrails Issues (`gri`)

A focused BMad module for GitHub issue triage: a dated local registry of open issues with work states and recorded backlog decisions, work sessions, readiness checks before development, and a closing verification that the code covers every acceptance criterion.

This is a focused BMad module in the [Guardrails](https://github.com/mlarese/bmad-module-guardrails)
bundle. It keeps the same behavior and shared memory while installing only the figures and
workflows for the issues area.

> **Generated.** This repository is produced by `tools/build_modules.py` in the
> [bmad-module-guardrails](https://github.com/mlarese/bmad-module-guardrails) repository.
> Make changes there and regenerate; local changes here will be overwritten.

## Agents

| Agent | Role | Skill | Focus |
| ----- | ---- | ----- | ----- |
| 📋 Tito | Issue Triage & Backlog Steward | `grl-agent-issues` | GitHub issues, backlog and triage, work states, readiness before development, hold signals, recorded decisions, duplicates, and dependencies. |

## Skills and workflows

| Skill | Purpose |
| ----- | ------- |
| `gri-profile` | Project profile | Collects the project context shared by every installed figure. |
| `gri-board` | Multidisciplinary review | Convenes the relevant figures on one artifact and returns a review summary or release verdict. |
| `grl-issues` | GitHub issue registry | Keeps a dated local registry of open issues with one work state each and the decisions taken on the backlog, syncs incrementally, and opens and closes work sessions. It reads GitHub only. |
| `grl-issue-readiness` | Issue readiness check | Applies seven criteria with citations, detects who already asked to wait, and publishes a single recognizable clarification comment after explicit confirmation. |
| `grl-issue-verify` | Issue closing verification | Maps every acceptance criterion onto the diff with file-and-line evidence, flags work no criterion asked for, and authorizes closing only when every criterion is covered. |
| `grl-issue-build` | Issue to implementation | Checks that the issue carries a written explanation — expected behavior, acceptance criterion, entry point, exclusions — builds a brief where every line cites its source, and hands the work to `bmad-build` only after an explicit authorization. |
| `grl-automation` | Controlled automation | Routes work from read-only checks through dry-run to observable execution, with explicit approvals and rollback. |

## Installation

```
bmad install gri
```

As a first step, run `gri-profile`. It collects the project profile — sector, data,
market, stack, and criticality — so each figure can calibrate its review. Without a profile,
the default remains `normal` and the figures start without context.

## Shared memory

The profile lives in `{project-root}/_bmad/memory/grl-shared/project-profile.md`, together
with `decisions.md` and `accepted-risks.md`. All Guardrails modules use the same path, so two
installed modules still share one profile.

## Using it with the bundle

This module installs skills with **the same names** as the `grl` bundle — `grl-agent-issues`
is identical in both. Do not install the full bundle and thematic modules in the same project:
choose the complete bundle, or only the thematic modules you need.

## License

MIT.
