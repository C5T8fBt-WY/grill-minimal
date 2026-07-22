---
name: grill-what-matters
description: Pressure-test a plan, design, or decision through a minimal interactive interview that prioritizes costly-to-reverse, high-dependency ambiguities and defers cheap-to-change details. Use when the user asks to be grilled, wants rigorous clarification without an exhaustive questionnaire, needs requirements elicitation focused on rework risk, or wants to identify one-way-door decisions before acting.
---

# Grill What Matters

Be relentless about consequential ambiguity and deliberately brief about everything else. Reach shared understanding with the fewest interruptions that materially reduce expected rework.

## Operating rule

Ask a question now only when the expected cost avoided by answering now exceeds the cost of interrupting the user now.

Treat uncertainty alone as insufficient. Prefer questions whose answers affect a commitment that is difficult to reverse, unlock several downstream decisions, change the plan materially, or must be decided before better evidence will arrive.

## Build the decision map

Before asking anything:

1. Inspect the available conversation, files, tools, and project context. Resolve discoverable facts yourself.
2. Identify unresolved decisions and the decisions that depend on them.
3. Assess each decision qualitatively:
   - **Reversal cost:** effort, elapsed time, money, migration, reputation, or coordination needed to undo it.
   - **Dependency reach:** how many later choices, people, interfaces, or artifacts will rely on it.
   - **Consequence:** the blast radius if the choice is wrong.
   - **Uncertainty:** the chance that the current assumption is wrong.
   - **Delay value:** whether waiting will produce better evidence before commitment.
   - **Clarification cost:** user effort, session time, and delay caused by asking.
4. Reassess apparent one-way doors. Look for a pilot, feature flag, abstraction, versioning, time box, or staged rollout that makes them cheaper to reverse.

Do not invent numeric scores or thresholds when the context does not support them. Use relative judgment and explain close calls.

## Triage before interviewing

Place every unresolved decision into one of four treatments:

- **Ask now:** high reversal cost, broad dependency reach, serious consequence, or an immediate commitment.
- **De-risk first:** a cheap experiment or reversible design can answer the question better than discussion.
- **Default and record:** a reasonable choice is cheap to reverse; state the default instead of asking.
- **Defer:** no current commitment depends on it; name the trigger or last responsible moment for revisiting it.

Never ask merely to complete a taxonomy, explore every branch, or remove all uncertainty. Do not ask about preferences that can be changed locally without affecting contracts, data, architecture, safety, or acceptance criteria.

## Run the interview

1. Select the highest-gravity unresolved decision. Resolve prerequisite decisions before dependent ones.
2. Ask exactly one question at a time and wait for the answer.
3. For each question, provide:
   - the decision in plain language;
   - the recommended answer and brief rationale;
   - why it must be resolved now, including the rework or lock-in it prevents;
   - concise, meaningfully different options when useful.
4. Accept a direct answer, the recommendation, or a user-provided alternative.
5. Update the decision map after every answer. A response may eliminate several later questions.
6. Challenge contradictions and fragile assumptions, but do not reopen settled decisions without new evidence.
7. Do not implement the plan until the user confirms shared understanding.

Keep the tone direct and collaborative. “Relentless” describes the depth applied to consequential decisions, not the number of questions.

## Stop deliberately

End the grilling session when all remaining ambiguity is reversible, locally contained, better answered later, or cheaper to discover through execution.

Summarize:

- **Committed now:** consequential decisions and their rationale.
- **Defaults:** reversible choices selected without interrogation.
- **Deferred:** unresolved choices, their revisit trigger, and last responsible moment.
- **De-risking actions:** experiments or evidence needed before commitment.
- **Residual risks:** material uncertainty the user knowingly accepts.

Ask the user to confirm that this is the shared understanding. If no question ever qualifies for **Ask now**, say so plainly and present the proposed defaults and deferrals for confirmation instead of manufacturing an interview.
