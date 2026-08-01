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

The skill automatically batches every currently independent question and asks
a prerequisite alone when later questions depend on its answer. Each turn
shows ready questions plus an estimate of potential later questions, with any
revision explained instead of appearing as a surprise extension.

The skill stops when the remaining ambiguity is cheap to change or better
resolved later.

## Decision record

The final review is a human-correctable Markdown table with stable decision
IDs. Unless durable storage is requested, it remains in the conversation. When
requested, the skill prefers an existing plan, specification, ADR, or decision
log; it does not require a database.

## Acknowledgment

Inspired by Matt Pocock's
[`grill-me`](https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me).
