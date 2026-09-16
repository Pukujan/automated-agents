# Storage and FOSSIL integration

## One authority per kind of information

- GitHub repository: generic plan, policy, source, prompts, and contracts.
- GitHub issues initially: development assignments and blockers.
- Private FOSSIL pack: source evidence, hypotheses, critiques, decisions, and outcome lineage.
- Local operational state: visit queue, leases, retries, schedules, checkpoints, and routine logs.
- Derived reports/tables: Markdown, CSV, SQLite, and live views; retain original evidence references.

Use the existing FOSSIL library with a pinned revision. Do not put personal research in the public fossil-core source repository.

## Minimal adapter proposal

The future adapter must save source bytes, return their identity/hash, read only allowed packs, then prepare, validate, commit, and read back proposal records.

Propose alone is not a saved record. A persisted claim.proposed records that an idea was proposed; it does not establish support or authorize execution. Keep evidence status separate from execution status and profile adoption.

## Proposal contents

Store the hypothesis, proposing actor/module version, intended audience/context, rationale, supporting and conflicting evidence references, assumptions/gaps, alternatives, proposed experiment, success/reconsideration criteria, review date, execution decision, and decision owner.

New evidence creates a linked event; it must not erase the earlier proposal.

## Privacy and durability

Private means outside public Git history, not encrypted by default. Keep browser credentials/session state out of captures. A local FOSSIL save survives a process restart, but does not by itself demonstrate off-device backup or protection from disk loss. Record that limitation in each receipt.
