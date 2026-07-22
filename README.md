# grill-minimal

Grill the decisions that create expensive rework. Defer the ones that do not.

This repository contains `grill-what-matters`, an agent skill for pressure-testing plans without turning every unresolved detail into an interview. It prioritizes decisions that are costly to reverse, constrain downstream work, or must be settled before an imminent commitment.

## How it behaves

The skill sorts unresolved decisions into four treatments:

- **Ask now** when a wrong or delayed answer creates meaningful lock-in or rework.
- **De-risk first** when a cheap experiment can answer better than discussion.
- **Default and record** when a reasonable choice is easy to reverse.
- **Defer** until the last responsible moment when no current commitment depends on it.

It asks one question at a time, includes a recommended answer, and stops when the remaining ambiguity is cheap to change or better resolved later.

## Install

From a local clone:

```powershell
npx skills add . --skill grill-what-matters --global --agent codex
```

After the repository is published:

```powershell
npx skills add <owner>/grill-minimal --skill grill-what-matters
```

The skill uses the portable `SKILL.md` format. Agent-specific interface metadata is included for Codex under `agents/openai.yaml`.

## Use

Invoke the skill explicitly:

```text
Use $grill-what-matters to pressure-test this plan.
```

It is also designed to trigger for requests such as “grill this plan,” “clarify only what would cause rework,” or “find the one-way-door decisions before implementation.”

## Package

```text
skills/
└── grill-what-matters/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```
