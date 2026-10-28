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

1. Interpret the user's task, symptoms, constraints, question type, and required facts.
   Form hypotheses about relevant domains and cross-cutting aspects from meaning, even if their names never occur in the request.
2. Read the base index and compact `by-meaning/index.md` routes for relevant types;
   consult domain and canonical Aspect definitions when they disambiguate the task.
3. Find candidate meanings and extension triggers through mechanisms, effects,
   questions, aliases and facets. Search bounded descriptions/snippets before
   opening full records; exact-word matches only generate candidates.
4. Read the selected group's compact `index.md`. Select applicable extensions,
   including required dependencies and contradictions, before reading local accounts.
5. Read one selected `core.md` explanation plus the necessary unique extensions.
   Follow every applicable `required_extensions` dependency (`path`/`when`);
   legacy plain links are unconditional. Unknown applicability is a reason to inspect or
   state a conditional result, not silently omit a material restriction.
6. Verify the selected claims in suitable source-local cards and original passages.
   Locate the exact evidence anchor and read its bounded logical passage first;
   expand for necessary premises rather than dumping a multi-topic text file or
   an entire chapter by default. Log unavoidable extra reads honestly in evaluations.
   Use a sufficient representative witness per equivalent claim by default;
   additional sources are necessary for disagreement, requested comparisons,
   weak/missing evidence, or other material differences.
7. Expand only the context needed for the question. Follow
   [semantic deduplication](deduplication.md#search-before-reading-repetitions):
   do not open every equivalent source or `confirmations.md` by default.

If text search is unavailable, inspect directory indexes and candidate files.
If semantic groups are absent, partial or unclear, use bounded legacy catalog/local
search and source text. Apply claim-level deduplication to the candidates you can
verify; do not assume unreviewed entries are duplicates or silently omit unmigrated
sources. Search remains read-only, including during a partially migrated KB.
Keep several possible branches for complex questions.
Return to another branch when evidence does not answer the question.
Follow the facet search contract: prioritize matching facets, retain adjacent-domain
and unclassified branches, and use hard domain/tag filters only for explicit user scope.
Do not require all requested aspects to be tagged on the same card.
Read each aspect relation's statement, conditions, inference status, and source evidence before treating a tag as applicable.

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
- Confirm inferred aspects from causal mechanisms and consequences, not repeated labels.
- Check whether a named aspect is only incidental or bibliographic; do not treat it as substantive evidence.
- Reopen the outside-facet branch even when the first branch produced plausible results; an initially inferred domain may hide a better explanation or prerequisite.
- Keep each claim attached to its source and edition. Respect explicit source scope
  when selecting witnesses; an out-of-scope baseline is navigation, not admissible
  support. An in-scope extension does not imply its source confirms the whole core.
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
6. Relevant aspect effects with their conditions and any indexer inference or cross-domain application made explicit.

Use short exact excerpts when practical.
Keep equations, units, negation, and conditions.
Label paraphrases and any new deductions.
Remove duplicate claims from the returned context while keeping their provenance
available. Compare and suppress equivalent candidates before full reads wherever
verified routing permits; shortening the final answer cannot recover context already
spent reading duplicates. Keep differences between source descriptions and all
necessary conditions, even when they increase the context.
Keep navigation summaries out of the evidence set.

If the user requests an answer, give it with source citations.
Mark any new implementation example as an example you created.
If evidence is insufficient, state what remains unknown.
Do not fill evidence gaps with model memory.

A compact evidence set does not remove earlier file reads from the current conversation.
