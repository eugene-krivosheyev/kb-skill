# Search Procedure

Resolve the KB path with the location rules in `SKILL.md`.
If the selected KB does not exist:

- Report its resolved path.
- Stop the search.

Do not create a KB during search or use the skill directory as a fallback.
Keep the base unchanged during search.
Use all indexed sources unless the user limits the scope.
A normal search need not read every source.
Do not restrict the search to the first matching source.

## Select the Evidence

1. Identify the question type, required facts, conditions, and requested aspects.
2. Read the base index and applicable catalog indexes.
3. Find candidate cards through descriptions, terms, aliases, and questions.
4. Search available text for exact names, identifiers, and alternative terms.
5. Read applicable local cards from suitable sources.
6. Read the linked source passages before using their claims.
7. Expand the evidence through necessary context and relations.

If text search is unavailable, inspect directory indexes and candidate files.
If a catalog entry is absent or unclear, inspect local indexes and source text.
Keep several possible branches for complex questions.
Return to another branch when evidence does not answer the question.

| Question | Evidence to seek |
| --- | --- |
| What is a concept? | Definition, scope, purpose, mechanism, example, and important distinctions. |
| How can I do a task? | Candidate solutions, conditions, steps or mechanism, dependencies, limits, and checks. |
| How does an aspect apply? | Relevant effects, conditions, costs, constraints, and alternatives across the requested scope. |

For a task, compare solutions against the user's conditions.
If important conditions are unknown, state assumptions or present conditional choices.
Include aspects that change the choice or correct use of a solution.
Do not add every aspect to a simple definition.

## Expand and Check

- Read the enclosing section when a passage depends on its argument or example.
- Read prerequisite definitions and linked conditions.
- Check nearby qualifications and exceptions.
- Read consequences that apply to the requested aspects.
- Compare descriptions in other sources when they can change the answer.
- Keep each claim attached to its source and edition.
- Distinguish source disagreement from different assumptions or scope.

For each part of the question, identify the supporting passages or the remaining gap.
Do not use a fixed number of passages for every question.
Stop when evidence is sufficient or the available search budget ends.
If the budget ends first, report incomplete coverage.

For complete lists or absence claims, check the full applicable scope.
Check that scope against source coverage records.
An empty text search does not prove absence.
Do not infer an unsupported link between facts from different sources.

## Return the Context

Return a compact evidence set in the requested language.
Include these items when applicable:

1. The interpreted question, source scope, and assumptions.
2. Source excerpts with evidence IDs and exact links.
3. Necessary definitions, conditions, and qualifications.
4. Applicable aspect effects and alternative solutions.
5. Disagreements, missing evidence, and limits of search coverage.

Use short exact excerpts when practical.
Keep equations, units, negation, and conditions.
Label paraphrases and any new deductions.
Remove duplicate evidence.
Keep differences between source descriptions.
Keep navigation summaries out of the evidence set.

If the user requests an answer, give it with source citations.
Mark any new implementation example as an example you created.
If evidence is insufficient, state what remains unknown.
Do not fill evidence gaps with model memory.

A compact evidence set does not remove earlier file reads from the current conversation.
