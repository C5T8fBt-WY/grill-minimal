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
2. Identify both stated and latent unresolved decisions. Infer prerequisites implied by the user's commitments even when the user did not list them. Map which later decisions and implementation steps depend on each one.
3. Assess each decision qualitatively:
   - **Reversal cost:** effort, elapsed time, money, migration, reputation, or coordination needed to undo it.
   - **Dependency reach:** how many later choices, people, interfaces, or artifacts will rely on it.
   - **Consequence:** the blast radius if the choice is wrong.
   - **Uncertainty:** the chance that the current assumption is wrong.
   - **Delay value:** whether waiting will produce better evidence before the first dependent commitment.
   - **Clarification cost:** user effort, session time, and delay caused by asking.
4. Reassess apparent one-way doors. Look for a pilot, feature flag, abstraction, versioning, time box, or staged rollout that makes them cheaper to reverse.

Do not invent numeric scores or thresholds when the context does not support them. Use relative judgment and explain close calls.

## Triage before interviewing

Place every unresolved decision into one of four treatments:

- **Ask now:** high reversal cost, broad dependency reach, serious consequence, or an immediate commitment.
- **De-risk first:** a cheap experiment or reversible design can answer the question better than discussion.
- **Propose a default:** a reasonable choice is cheap to reverse; record it as a proposal instead of interrupting the user.
- **Defer:** no current commitment depends on it; name the trigger or last responsible moment for revisiting it.

Never ask merely to complete a taxonomy, explore every branch, or remove all uncertainty. Do not ask about preferences that can be changed locally without affecting contracts, data, architecture, safety, or acceptance criteria.

Do not use a distant launch, announcement, or delivery date as evidence that a decision can wait. Set its last responsible moment immediately before the earliest dependent code, schema, contract, purchase, public promise, or other costly commitment.

## Maintain the decision inventory

Keep a transient working decision inventory in model context during the interview. Assign each item a stable ID such as `D1`. Track the decision, treatment, current or proposed answer, rationale, dependencies, revisit trigger, and status.

Treat every proposed default as unconfirmed until the user approves the final summary. The user may correct any item by ID at any time. Update the existing item rather than leaving contradictory versions. Do not silently turn a model-selected default into a human decision.

Use a Markdown table as the portable review format at the confirmation boundary, with columns for ID, treatment, decision, answer or status, and rationale or revisit trigger. Model context is working state, never the durable source of truth. Do not create a database or write a file merely to run the interview. Persist the confirmed inventory only when the original request names a target artifact or the user explicitly asks for persistence; prefer an existing plan, specification, ADR, or decision log over a new file. State whether the inventory exists only in the conversation or at a durable path.

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
6. Derive new prerequisites from every accepted answer. For example, a data-loss guarantee may force a canonical data representation decision even if the user never mentioned one.
7. Challenge contradictions and fragile assumptions, but do not reopen settled decisions without new evidence.
8. Do not implement the plan until the user confirms shared understanding.

Keep the tone direct and collaborative. “Relentless” describes the depth applied to consequential decisions, not the number of questions.

## Stop deliberately

Before stopping, run a commitment-readiness check: for every committed high-gravity decision, verify that no unresolved prerequisite must be settled before its first dependent implementation or external commitment.

End the grilling session only when that check passes and all remaining ambiguity is reversible, locally contained, better answered later, or cheaper to discover through execution.

Summarize:

- **Committed now:** consequential decisions and their rationale.
- **Proposed defaults:** reversible choices suggested without interruption and still open to correction.
- **Deferred:** unresolved choices, their revisit trigger, and last responsible moment.
- **De-risking actions:** experiments or evidence needed before commitment.
- **Residual risks:** material uncertainty the user knowingly accepts.
- **Record location:** conversation only, or the durable artifact path requested by the user.

Ask the user to confirm that this is the shared understanding. If no question ever qualifies for **Ask now**, say so plainly and present the proposed defaults and deferrals for confirmation instead of manufacturing an interview.
