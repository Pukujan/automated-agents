# Research and strategy system — living plan

Status: implementation proposal grounded in the user's stated requirements. This records a reconstructed discussion summary, not a verbatim transcript.

## Requirements

- Start useful work early and build in slices.
- Agents own bounded reasoning and recommendations, not only mechanical tasks.
- Separate research, brand stewardship, strategy, and execution responsibilities.
- Every strategy is a proposal; preserve hypotheses and revisions durably.
- Use local computer/browser interaction with an existing logged-in session for research collection.
- Explore relevant posts, profiles, comments, visible engagement, companies, and related sources.
- Operate slowly with explicit limits, visibility, and the ability to intervene.
- Keep context scoped and prevent unreviewed generated content becoming established memory.
- Keep the reusable engine separate from personal data.

## Ownership

| Layer | Owns | Does not own |
| --- | --- | --- |
| Collector | Observed page data, source references, coverage receipts | Strategic conclusions or brand changes |
| Research | Questions, candidate selection, evidence-backed findings and gaps | Treating a selected sample as the whole market |
| Brand | Positioning/voice proposals and consistency assessment | Inventing personal experience or silently changing the approved profile |
| Strategy | Audience/campaign proposals, alternatives, experiment criteria | Declaring its own hypothesis proven or granting publication authority |
| Controller | Budgets, pacing, checkpoints, pause/resume | Deciding what is true |

For a career-targeted run, the decision path is deliberately small:

```text
target researcher -> evidence packet -> hiring-manager judge
                                      -> career coach
                                      -> strategy proposal -> owner decision
```

The hiring manager owns the fit assessment. The career coach owns the evidence and relationship plan. The strategy agent owns the recommended campaign or job-search direction. None of these roles owns external action. A subagent invocation is a fresh, scoped case packet—not a shared conversational memory—so each result can be independently stored, inspected, rejected, or rerun.

### Agent result envelope

Every role returns a small versioned envelope before any role-specific fields:

```yaml
case_id: case_unity_20260916
run_id: run_...
agent: hiring_manager
agent_version: 0.1
prompt_version: 0.1
schema_version: 0.1
status: complete
input_refs: [artifact_...]
output_refs: []
findings: []
missing_data: []
recommendations: []
open_questions: []
prohibited_actions: []
confidence: low
```

The controller saves the complete response as an immutable research/assessment artifact and emits a proposal event that points to it. SQLite can hold pending runs, frontier items, retries, and pause state; FOSSIL holds the durable evidence, agent assessments, hypotheses, and approved/rejected decisions. The public repository holds only the generic contracts and prompts.

### First Unity career slice

Begin with one company and one or two live role snapshots, not a company-wide crawl. The initial Unity fit hypothesis is the Senior Backend Engineer, AI Platform & Infrastructure role because its official description overlaps the owner's current AI-systems themes; it remains unproven until seniority, production-scale, cloud, and eligibility evidence are collected. Compare it with Staff Software Engineer, Gaming AI only if the first evidence packet leaves the fit ambiguous.

The first useful run should produce four inspectable outputs: (1) official role evidence, (2) a strict requirement scorecard, (3) a prioritized seven-day coaching plan, and (4) a strategy proposal with explicit assumptions and a review date. Stop there. Do not build networking automation or application automation until the owner has reviewed the assessment and approved the next research question.

## Exploration model

Use a priority queue of discovered destinations. Each entry has a reference, discovered-from reference, reason to visit, depth, status, and last-capture time. The research agent ranks candidates in batches with explicit reasons, considering novelty, competing explanations, and collection cost.

Discover only observed links and relationships. Keep inferred links and topic labels separately marked as model annotations. Company-to-company jumps require a visible connection or an explicit new search. Exploration graphs can contain cycles; deduplication and revisit windows govern browsing.

A dependency DAG can describe a batch: capture -> extraction -> findings -> strategy proposal. It is not the model for all browsing. Beads remains optional task coordination; GitHub issues coordinate initial development.

## Targeted research briefs

The controller starts from a brief, not from an unrestricted crawl. A brief may name one or more seed types:

- a company page or company search, with target roles, location, and hiring/application context;
- the owner's connection list, optionally filtered by visible company, role, location, or relationship;
- a job post, recruiter, candidate, creator, or post URL;
- a topic/search phrase, with an explicit audience and evidence goal.

Each frontier item records `node_type`, canonical URL or platform ID, `discovered_from`, `edge_type`, `depth`, `selection_reason`, `relevance_score`, `status`, and `last_observed_at`. The controller deduplicates IDs and selects the next item by relevance to the brief, evidence value, novelty, diversity, and visit cost.

Typical allowed edges are:

```text
company -> visible people/search results -> public profile -> public activity
connection list -> visible connection -> public profile -> current company/posts
job post -> company/recruiter -> public profile -> relevant activity
post -> author/comments/reactions -> public profiles -> associated company/posts
```

The agent may record a candidate or company as a research entity, rank fit, and state uncertainty. It may not contact a candidate, send a connection request, apply for a job, or treat an inferred company relationship as observed fact. A company target is configured in the research brief; it is never guessed from a random profile hop.

## Data and interpretation

Collect timestamped structured records first; generate Markdown and tables from the same records. Capture post, comment/reply, visible reaction, profile/company excerpt, metric snapshot, and capture receipt separately. Keep observed values, calculations, platform estimates, and model interpretations distinct.

Missing is not zero. A partial later capture is not evidence of deletion. A personalized feed is a sample. Sources from one connected discussion are not independent confirmations.

## Browser behavior

One active worker; sequential actions; page-settle waits; configurable modest pauses. Pacing is workload control, not an assurance about platform treatment. The controller, rather than model output or page text, enforces budgets and tool scopes.

The first pilot proposes 15 minutes, at most 20 distinct pages, depth two, and a per-thread expansion limit. These are workload choices, not platform-safe thresholds. The user can pause, step, skip, or take over; resume re-observes the actual page.

Collection is initial scope. Messaging, connection requests, reactions, publishing, and profile edits are separate actions. Save progress and stop on access challenges, changed login state, or repeated errors.

## Build sequence

1. Preserve requirements, open design choices, and untested hypotheses.
2. Run one visible, bounded research exploration that yields a structured capture and evidence brief.
3. Derive only repeatable search/open/expand/extract operations from observed pages; verify interruption recovery.
4. Turn research into brand and strategy alternatives with evidence, assumptions, and review triggers.
5. Add recurring collection only after a successful repeat run.
6. Add separate X page handling while sharing queue, storage, and provenance contracts.

Luna is a candidate for bounded exploration, candidate selection, and navigation repair. Scripts perform repeatable extraction. Actual tool access and behavior must be verified.

## Current unknowns

A manual supervised Brave observation has now verified the profile -> post -> post analytics -> content analytics -> older post -> visible commenter profile path. No automated crawler, recurring schedule, analytics export, or campaign experiment has run. The next seed (target company, job, connection-list filter, or topic search), browser bridge, profile inputs, unattended execution, and backup destination remain open. No strategy, brand positioning, paid outreach service, Beads installation, graph database, or orchestration framework has been selected.
