# Index Procedure

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

Describe tasks without the solution name.
Keep the author's solution type as an optional detail.
Do not invent missing benefits, steps, assumptions, or relations.
Keep translations and interpretations separate from the author's wording.

## Connect the Base

1. Register each source in `<KB>/sources/index.md`, including partial imports.
2. Update local indexes in source order where order matters.
3. Connect local cards to the shared catalog by meaning.
4. Keep uncertain term matches separate.
5. Record source-specific differences beside catalog links.
6. Update affected catalog entries when a source changes.
7. Link the shared source list and catalog from `<KB>/index.md`.

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

Keep `coverage: partial` if the original is missing or content remains unread or unavailable.
Report the resolved KB path, source IDs, original paths, coverage, gaps, and unresolved term matches.
Describe the checks you performed. Do not claim automatic validation.
