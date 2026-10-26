# Index Procedure

## Completion and Progress

Treat indexing as unfinished until all requested source sections have been read,
useful evidence cards and catalog entries have been made, and the result has been checked.
Extracting every file or indexing summaries alone does not complete the request.

Keep working through accessible material after each checkpoint.
`coverage: partial` records an intermediate state; it is not permission to end early.
Do not stop merely because the source is long, a first pass is useful, or the current
context is filling. Save the next exact unread location and continue after compaction.
Do not ask the user to say “continue” for work already requested.

Before starting, tell the user the source scope, existing coverage, and next stage.
During work, report completed chapters or sections, what changed in the index,
and what comes next. Send concise updates at meaningful milestones and at least
once per minute while work continues. Use verified counts and a stated denominator;
do not invent percentages or remaining-time estimates. Distinguish text retained,
text actually read, figures reviewed, cards created, and checks completed.

For long sources, use parallel reader agents when delegation is available.
Assign nonoverlapping, contiguous chapter ranges and explicit file ownership.
Each reader must read its full assigned text in source order, including notes,
examples, tables, and relevant figures; report exact coverage and any gaps.
The coordinator owns shared indexes and the coverage record, reconciles reader
results in source order, and checks that no section was skipped or counted twice.
Delegation does not relax the tool restrictions or evidence requirements.

Keep outputs small enough to read without truncation. A truncated or omitted
passage remains unread until the missing portion has been retrieved and read.
Read diagrams and graphical equations with available image tools, in context;
copying their image files does not count as reading them.

Stop before completion only when the user pauses or narrows the task, or a concrete
access, permission, input, or tool limitation prevents further useful work.
Try available alternatives and finish unaffected sections first. Explain the exact
remaining blocker, preserve the checkpoint, and label the outcome incomplete.
Do not present a checkpoint as a final success. Mark `coverage: complete` only
when the coverage list has no unread or unavailable source content and the checks pass.

## Open the KB

Resolve the KB path with the location rules in `SKILL.md`.
Open that KB, or create it if it does not exist.
Read existing shared indexes before adding sources.
Create missing shared indexes.
Add every source under this root's `sources/` directory.
Keep existing sources and catalog entries.
Do not create a separate KB root for each book.

## Read the Source

1. Check the available sources and the target base.
   Keep input files unchanged.
2. Read existing source records before an update.
3. Give each new work and edition a separate source ID.
4. Record the source identity and original location.
5. Keep its unchanged original in the source package.
6. Read the source structure before you divide its text.
7. Read the content in source order, in manageable parts.
8. Update the coverage list after each part.

Read the main narrative, code, equations, tables, captions, notes, and bibliographies.
Use summaries to navigate or consolidate, never as a replacement for the main text.
Card selection is based on usefulness, not a fixed quota per chapter.

If the original is already retained, use that file without another copy.
Reuse a stored original only after you confirm that its content matches.
Do not match originals by filename or title alone.
If the original cannot be retained, record this gap.

If the content cannot be read with available tools, record the gap.
Do not mark unread content as complete.
For a repeated source, continue from unread sections.
Recheck unavailable sections only when access changes.
Do not overwrite another edition or unrelated user content.

## Divide the Text

Use the source structure first.
Select boundaries by meaning, not a fixed token count.
Keep each unit large enough to understand its claim or action.
Use smaller units only when they keep the necessary context.
Use links to expand context instead of routine text overlap.

| Material | Keep together |
| --- | --- |
| Definition | The meaning, scope, and qualifications. |
| Explanation | One argument and its necessary premises. |
| Solution | The problem, mechanism, and conditions, or explicit links between them. |
| Procedure | Preconditions, ordered steps, expected result, and warnings. |
| Equation | Symbols, assumptions, units, and limits. |
| Table or figure | Labels, caption, notes, and the applicable discussion. |
| Example | The setup, code or calculation, and the explanation. |

If a solution spans several units, link its parts from one card.
Do not rewrite the source as a set of isolated facts.
Keep the author’s narrative and reading order.

## Make the Cards

1. Identify concepts, tasks, solutions, and aspects supported by the source.
2. Write a short description for each useful card.
3. Add evidence links for each statement about the source.
4. Add the source's names, abbreviations, and useful alternative terms.
5. Add questions that the linked passages can answer.
6. Link necessary definitions, conditions, examples, limits, and consequences.
7. Record aspect effects where the source discusses them.
8. Assign subject domains and derive cross-cutting tags using the facet model.
   Read mechanisms and consequences even when the aspect's name is absent.
   For each tag add its local Aspect relation, conditional statement, and exact source evidence.
   Reject tags supported only by keyword occurrence or presumed general applicability.

Describe tasks without the solution name.
Keep the author's solution type as an optional detail.
Do not invent missing benefits, steps, assumptions, or relations.
Keep translations and interpretations separate from the author's wording.

Review every card for facet classification, including cards with no justified tags.
Use empty lists deliberately; do not invent tags to make every record look populated.
For a metadata-only migration, reuse verified retained originals and text, inspect cards and relevant evidence, and preserve established text coverage.
Parallel readers may own nonoverlapping card ranges during such a migration; the coordinator owns shared vocabularies, source summaries, and catalog projections.

## Connect the Base

1. Register each source in `<KB>/sources/index.md`, including partial imports.
2. Update local indexes in source order where order matters.
3. Connect local cards to the shared catalog by meaning.
4. Keep uncertain term matches separate.
5. Record source-specific differences beside catalog links.
6. Update affected catalog entries when a source changes.
7. Link the shared source list and catalog from `<KB>/index.md`.
8. Update source facet summaries, domain vocabulary, and canonical Aspect/tag entries.
9. Project local domains and tags into the catalog and rebuild affected navigation.

Keep existing entries when updating shared indexes.
Before a partial import stops, save its source entry and coverage record.

Use short descriptions that show useful details, limits, and exceptions.
Divide an index when its entries become difficult to select.
Keep enough detail to choose a branch without opening every file.

## Check the Result

- Check every source section against the coverage list.
- Check that the original is retained without duplicate archive copies.
- Check that every imported source is reachable from the shared root index.
- Check local links without relying on the catalog.
- Check evidence anchors and original locations.
- Check required OKF frontmatter and index structure.
- Check concept discovery with a different term.
- Check task discovery without a solution name.
- Check an aspect discussed far from the main explanation.
- Check a definition with its limits and necessary context.
- Check domain and tag IDs against the shared vocabularies.
- Check that each tag has a local Aspect target and exact source evidence; compare tag sets with relation tag sets.
- Check substantive classification on passages that omit the tag words, and reject passing keyword mentions.
- Check discovery from symptoms without domain/aspect labels, unclassified-card fallback, and a cross-domain application.
- Check that catalog facets agree with their linked cards and that original text and stable IDs survived metadata migration.

Keep `coverage: partial` if the original is missing or content remains unread or unavailable.

## Report the Result

Report the indexing outcome in the agent chat.
Include the resolved KB path, source IDs, original paths, coverage, gaps, unresolved term matches, and a summary of created or updated files.
Describe the checks you performed. Do not claim automatic validation.

Keep durable source identity, provenance, edition or version, coverage, and gaps in `source.md`.
Keep execution logs, file counts, and check summaries in the chat, not in `source.md`.
Do not create `report.md` or another indexing report in the KB, or link one from KB indexes, by default.
Create a separate report file only when the user explicitly requests it.
Unless the user specifies its location, save that report outside the KB.
