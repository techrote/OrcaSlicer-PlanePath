# PlanePath RAG index

This directory is the canonical context pack for autonomous work on **OrcaSlicer-PlanePath**.

## Retrieval order

For every implementation issue, read:

1. `00-PROJECT-BRIEF.md` — scope, definitions, success criteria, and non-goals.
2. `01-UPSTREAM-SEAM-MAP.md` — where the current OrcaSlicer implementation actually lives and the behaviours that must remain authoritative.
3. The architecture document(s) named by the issue.
4. `06-TEST-CI-STRATEGY.md` — test evidence and merge gates.
5. `08-REVISED-ROADMAP.md` — issue dependencies and intended delivery order.
6. `09-AUTONOMOUS-EXECUTION-CONTRACT.md` — branch/PR/CI/merge/verification rules.

Read `07-PLAN-REVIEW.md` whenever changing architecture or scope; it records rejected shortcuts and why they were rejected.

## Topic routing

| Need | Read |
|---|---|
| Project purpose / v1 scope | `00-PROJECT-BRIEF.md` |
| Orca Hilbert / FillPlanePath implementation map | `01-UPSTREAM-SEAM-MAP.md` |
| Target components and data flow | `02-TARGET-ARCHITECTURE.md` |
| Lua API, manifests, quotas and sandbox | `03-SCRIPT-ABI-SANDBOX.md` |
| Trait model, config, serialization and project identity | `04-TRAITS-CONFIG-PORTABILITY.md` |
| Candidate curves and research leads | `05-CURVE-RESEARCH-CATALOG.md` |
| Tests, fixtures, CI and acceptance evidence | `06-TEST-CI-STRATEGY.md` |
| Critique of the first plan | `07-PLAN-REVIEW.md` |
| Dependency graph / issue campaign | `08-REVISED-ROADMAP.md` |
| Autonomous agent operating rules | `09-AUTONOMOUS-EXECUTION-CONTRACT.md` |

## Authority order

When documents conflict:

1. the current GitHub issue acceptance criteria;
2. `09-AUTONOMOUS-EXECUTION-CONTRACT.md`;
3. `08-REVISED-ROADMAP.md`;
4. architecture/sandbox/config documents;
5. upstream seam map;
6. project brief.

If current OrcaSlicer upstream has moved, refresh the seam map facts in the implementing PR rather than forcing stale paths onto new code.
