# grill-minimal

Grill the decisions that create expensive rework. Defer the ones that do not.

This repository contains `grill-what-matters`, an agent skill for
pressure-testing plans without turning every unresolved detail into an
interview. It prioritizes decisions that are costly to reverse, constrain
downstream work, or must be settled before an imminent commitment.

## How it behaves

The skill sorts unresolved decisions into four treatments:

- **Ask now** when a wrong or delayed answer creates meaningful lock-in or rework.
- **De-risk first** when a cheap experiment can answer better than discussion.
- **Propose a default** when a reasonable choice is easy to reverse.
- **Defer** until the last responsible moment when no current commitment
  depends on it.

It first asks whether the user prefers one question per turn or small batches.
Every substantive turn shows resolved decisions and currently known remaining
work. The skill includes recommended answers, discovers hidden prerequisites
implied by accepted decisions, and stops when the remaining ambiguity is cheap
to change or better resolved later.

## Interaction and progress

Single-question mode preserves dependency order. Batch mode groups no more than
three independent high-gravity questions; questions whose answers affect one
another remain sequential. The user can switch modes during the interview.

Progress is deliberately bounded rather than presented as a fake percentage:

```text
Progress: 2 resolved · 1 known ask-now · 3 deferred or defaulted · mode: single
```

The known count can change when an answer exposes a previously hidden
prerequisite. The skill calls out that change instead of silently extending the
session.

## Decision records

During the interview, the decision inventory lives transiently in the model's
working context. At the confirmation boundary, the skill renders it as a
human-correctable Markdown table with stable decision IDs, committed decisions,
proposed defaults, deferrals, de-risking actions, residual risks, and the record
location. Model context is not treated as durable storage.

Proposed defaults are not treated as human decisions until the user confirms or
corrects them. The skill does not require a database and does not create files
merely to conduct an interview. When durable storage is explicitly requested,
it prefers an existing plan, specification, ADR, or decision log; otherwise the
record remains in the conversation.

## Install

From a local clone:

```powershell
npx skills add . --skill grill-what-matters --global --agent codex
```

From GitHub:

```powershell
npx skills add C5T8fBt-WY/grill-minimal --skill grill-what-matters
```

[GitHub repository](https://github.com/C5T8fBt-WY/grill-minimal)

The skill uses the portable `SKILL.md` format. Agent-specific interface metadata
is included for Codex under `agents/openai.yaml`.

## Use

Invoke the skill explicitly:

```text
Use $grill-what-matters to pressure-test this plan.
```

It is also designed to trigger for requests such as “grill this plan,” “clarify
only what would cause rework,” or “find the one-way-door decisions before
implementation.”

## Package

```text
skills/
└── grill-what-matters/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```
