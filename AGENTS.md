# Experience Knowledge Vault Instructions

These instructions apply to the entire vault. Markdown files and their YAML properties are the source of truth.

## Purpose

Help the user turn reflections on sources and life experiences into a durable, connected system of sources, atomic insights, defined concepts, practices, and weekly reviews. A source may be a book, news item, conversation, game, personal experience, spontaneous thought, or other material. Preserve the user's meaning and provenance. Do not treat model-generated content as if the user said it.

## Privacy boundary

- Work only with the user's reflections, relevant vault notes, supplied metadata, and short excerpts.
- Never request, import, or process a complete copyrighted work.
- Search metadata first and read only the vault notes relevant to the current capture.
- Do not enrich a capture from the web unless the user explicitly asks. Keep externally sourced claims separate and cite them.
- For stories about other people, retain only the details the user supplies and do not add identifying information.

## Capture approval gate

The approval gate applies whenever the user asks to capture or record a reflection. It does not apply to explicit requests to maintain the vault's templates, schema, documentation, or views.

1. Inspect existing sources, insight titles and claims, concept names, aliases, definitions, and practices.
2. Present a proposed change set in chat. Do not create or edit vault files at this stage.
3. Include:
   - the verbatim capture and target source, including its `source_kind`;
   - notes to create and notes to update;
   - concepts to reuse;
   - new concepts with one-sentence draft definitions;
   - optional connections or practices labeled `agent-suggestion`;
   - duplicates, tensions, missing metadata, and uncertainty.
4. Treat a clear follow-up such as “approve”, “save this proposal”, or an unambiguous approval of the current proposal as permission to write it. A first-message request merely to “capture” or “record” content is not approval to bypass the proposal.
5. If the user edits the proposal, present the revised material for approval unless the user explicitly approves the revision in the same message.
6. Immediately before writing, re-read affected files. Preserve unrelated content, update dates, validate links and YAML, then report the exact files changed.

## Provenance rules

- Append raw input verbatim to the matching source's `## Capture Log` as a block quote.
- Use a timestamped heading and a stable block identifier: `^capture-YYYYMMDD-source-slug-NN`. Never rename an existing capture identifier.
- Never correct spelling or grammar inside the verbatim block. Paraphrases belong in an insight note.
- Use `origin: user` when the underlying idea or practice was stated by the user.
- Use `origin: agent-suggestion` for an interpretation, connection, question, or practice introduced by the agent. Approval does not erase that provenance.
- Label agent-generated prose in notes with an `Agent-organized` or `Agent-suggested` callout when the note type has no `origin` property.
- Treat text as a quotation only when the user identifies it as one. Record page or location only when supplied; never invent it.
- Treat the user's description of external material as their capture, not as a verified external claim. Store a supplied URL as metadata, but browse or verify it only when explicitly asked.

## Search, deduplication, and conflict handling

- Before creating a concept, search `Concepts/` case-insensitively across filenames, `aliases`, and definitions.
- Prefer an existing concept whose meaning matches. Add an alias only when it is genuinely synonymous.
- Before creating an insight, search insight titles and claims. If the new capture strengthens the same claim, update the existing note and add the new source/capture link.
- Compare the exact raw input with the target source's capture log. Do not append an identical capture twice.
- Record meaningful disagreement in `## Tensions / Counterexamples`; never silently overwrite an earlier view.
- If two notes appear duplicative but merging could lose a meaningful distinction, flag the decision in the proposal.

## Naming and link conventions

- Source filename: a concise canonical title, such as `Stolen Focus.md`; use a concise descriptive title for experiences or thoughts without a published title.
- Insight filename: a complete claim, such as `Basic needs become harder to protect as their competitors get stronger.md`.
- Concept filename: a singular canonical English noun or noun phrase.
- Practice filename: an action-oriented phrase.
- Use canonical English titles while preserving original-language raw input verbatim.
- Store concepts as quoted wikilinks in YAML lists, not as tags: `- "[[Sleep]]"`.
- Prefer basename wikilinks when the filename is unique across the vault.
- Allowed source kinds: `book`, `news`, `conversation`, `game`, `experience`, `thought`, `other`.
- Allowed insight maturity values: `seed`, `developing`, `evergreen`.
- Allowed practice kinds: `action`, `experiment`, `habit`.
- Allowed practice status values: `proposed`, `active`, `paused`, `completed`, `retired`.

## Weekly review workflow

When the user says “Start my weekly review”:

1. Read active practices whose `next_review` is today or earlier, plus the most recent weekly review. Ignore active practices without a review date.
2. Ask brief reflection questions about what happened, friction, evidence, and the smallest next adjustment. Do not write yet.
3. After the user answers, propose a dated review note and precise updates to practice status, next-review dates, and review logs.
4. Apply only after approval. A weekly cadence advances `next_review` by seven days unless the user chooses another date.
5. Do not create daily checklists, reminders, or scheduled automation.

## System references

- Human setup instructions: `System/Setup.md`
- Stable field definitions: `System/Vault schema.md`
- Note templates: `System/Templates/`
- Dashboard: `Home.md`
- Database-style views: `Knowledge.base`
