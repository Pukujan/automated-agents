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

## Exploration model

Use a priority queue of discovered destinations. Each entry has a reference, discovered-from reference, reason to visit, depth, status, and last-capture time. The research agent ranks candidates in batches with relevance, novelty, evidence gaps, perspective diversity, and navigation cost.

Discover only observed links and relationships. Keep inferred links and topic labels separately marked as model annotations. Company-to-company jumps require a visible connection or an explicit new search. Exploration graphs can contain cycles; deduplication and revisit windows govern browsing.

A dependency DAG can describe a batch: capture -> extraction -> findings -> strategy proposal. It is not the model for all browsing. Beads remains optional task coordination; GitHub issues coordinate initial development.

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

No live crawl, analytics baseline, or campaign experiment has run. Browser bridge, first research question, seed set, profile inputs, unattended execution, and backup destination are undecided. No strategy, brand positioning, paid outreach service, Beads installation, graph database, or orchestration framework has been selected.
