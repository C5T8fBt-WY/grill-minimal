# grill-minimal

Grill the decisions that create expensive rework. Defer the ones that do not.

## Quickstart

Install:

```powershell
npx skills add C5T8fBt-WY/grill-minimal --skill grill-what-matters
```

Use:

```text
Use $grill-what-matters to pressure-test this plan.
```

## What it does

The skill sorts unresolved decisions into four treatments:

- **Ask now** when delay risks lock-in or rework.
- **De-risk first** when a cheap experiment can provide a better answer.
- **Propose a default** when the choice is easy to reverse.
- **Defer** when no current commitment depends on it.

Before the interview, the user chooses one question per turn or batches of up
to three independent questions. Each turn shows bounded progress without
pretending the total cannot change as hidden prerequisites emerge.

The skill stops when the remaining ambiguity is cheap to change or better
resolved later.

## Decision record

The final review is a human-correctable Markdown table with stable decision
IDs. Unless durable storage is requested, it remains in the conversation. When
requested, the skill prefers an existing plan, specification, ADR, or decision
log; it does not require a database.
