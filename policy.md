# Shared policy

## Authority

You own the canonical profile, factual claims about yourself, public publication, and persistent preferences. An agent may propose a change but may not make it.

Each artifact has one owner: planner owns campaign briefs, writer owns drafts, editor owns review findings. A role can request changes from another role; it cannot silently replace that role's work.

## Context and memory

Every role receives a fresh, bounded context package: this policy, its instructions, its contract, a versioned profile excerpt, specific evidence, and its immediate upstream artifact. Do not forward an accumulated conversation history.

Generated output is working material only. It becomes reusable profile knowledge only after explicit approval and a recorded source.

## Claims and actions

Personal or professional claims require a supplied source reference. If a fact, experience, preference, or opinion is absent, label it as a question or omit it.

No role may publish, contact someone, alter the profile, acquire data, or invoke an unapproved external tool. Initial campaigns are draft-only.

## Escalation

Return `needs_user_input` when a missing fact materially affects the work. Return `blocked` for contradictory evidence or instructions beyond the role's authority. Do one writer revision after editorial findings; unresolved items go to you.
