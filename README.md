# SAERO

**SAERO** (새로) is an automated spherical parallel manipulator (SPM) telescope mount.

Mechanical design stays in SolidWorks. Software planning and documentation live in [`docs/`](docs/).

## Status

The repository is in early setup. Kinematics, actuators, and control software are still open. The two files under `docs/` are format samples for later plans and write-ups.

## Split of work

| Area | Where it lives |
| --- | --- |
| Mechanical design: structure, joints, actuators, CAD | SolidWorks files in this repository |
| Software planning: scope, milestones, open questions | [`docs/planning/`](docs/planning/) |
| Software documentation: settled behavior and interfaces | [`docs/`](docs/) |

## Layout

```text
SAERO/
├── README.md
├── LICENSE
├── docs/
│   ├── planning/              plans for a software slice
│   └── sample-documentation.md
└── (SolidWorks models)        added as the CAD progresses
```

SolidWorks lock files, backups, and simulation caches stay out of git. See [`.gitignore`](.gitignore).

## How a handoff is written

1. Open a plan in `docs/planning/` while a software slice is still being scoped. The plan holds the goal, the mechanical inputs it needs, milestones, and unanswered questions.
2. Move settled behavior into a documentation page under `docs/` once the plan is accepted. That page describes what the software does and how it meets the mount.
3. Leave mechanical questions in the plan until the CAD answers them. Software docs cite those answers. They do not invent joint limits, motor models, or frame origins.

Format samples:

- [Sample plan](docs/planning/sample-plan.md)
- [Sample documentation](docs/sample-documentation.md)

## License

[MIT](LICENSE). Copyright (c) 2026 MinJoon Kim.
