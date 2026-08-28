---
type: guide
created: 2026-08-28
updated: 2026-08-28
---

# Vault Schema

Markdown and YAML properties are the stable data interface. Concepts are notes linked through the `concepts` property; tags are not used as a substitute for concepts.

## Shared Rules

- Dates use `YYYY-MM-DD`.
- Internal links inside YAML are quoted, for example `"[[Sleep]]"`.
- Empty multi-value properties use `[]`.
- `created` records the first saved date; `updated` changes whenever substantive content changes.
- Raw captures remain verbatim inside the relevant source's capture log.

## Source

Required properties: `type: source`, `source_kind`, `created`, and `updated`.

- Source kind: `book`, `news`, `conversation`, `game`, `experience`, `thought`, or `other`.
- Optional metadata includes `creator`, `source_url`, `source_date`, and `engagement_status`. Record it only when applicable or supplied.
- Suggested engagement statuses when needed: `planned`, `in-progress`, `paused`, `completed`, or `abandoned`.

Required sections: Context, Capture Log, Insights, Practices, and Open Questions.

## Insight

Required properties: `type: insight`, `sources`, `concepts`, `maturity`, `origin`, `created`, and `updated`.

- Maturity: `seed`, `developing`, or `evergreen`.
- Origin: `user` or `agent-suggestion`.
- The filename and heading state a claim rather than only naming a topic.

Required sections: Claim, Original Observation, Why It Matters, Evidence / Examples, Tensions / Counterexamples, Related Practices, and Connections.

## Concept

Required properties: `type: concept`, `aliases`, `related_concepts`, `created`, and `updated`.

Required sections: Definition, Boundaries / Non-examples, and Relationships. A concept is not valid until it has a concise definition.

## Practice

Required properties: `type: practice`, `practice_kind`, `derived_from`, `concepts`, `origin`, `status`, `created`, and `updated`.

- Practice kind: `action` for a one-time behavior, `experiment` for a time-bounded test, or `habit` for repeated behavior.
- Status: `proposed`, `active`, `paused`, `completed`, or `retired`.
- Origin: `user` or `agent-suggestion`.
- `cadence` and `next_review` are optional when they do not suit a one-time action. An active practice appears in the due view only when `next_review` is set.

Required sections: Rationale, Cue, Smallest Viable Behavior, Success Signal, and Review Log.

## Weekly Review

Weekly reviews use `type: weekly-review` and live in `Reviews/`. They summarize the user's reflection and link to every practice they update. Practice changes still require approval before saving.
