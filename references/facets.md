# Domains, Tags, and Semantic Selection

## Distinct Meanings

- `domains` identify the subject areas of the material, not every field where it might be applied.
- `tags` identify substantive cross-cutting aspects derived from the material's meaning.
- `aliases` name the same object in other ways; `questions` describe answerable user intents.
- Aspect records define concerns; aspect relations explain relevance, effects, conditions, and evidence.

A topic, algorithm, product, or pattern name is not an aspect tag merely because it is searchable.
Use its card title, aliases, questions, and relations for discovery.
Domain and tag assignments are indexer metadata, not claims that the author used these labels.

## Shared Vocabulary

Use stable lowercase hyphenated IDs for domains and tags, stored as YAML lists.
Maintain domain records in `<KB>/domains/` with type `Domain`, `id`, title, description,
scope boundaries, and useful aliases. Keep the vocabulary in the selected KB, not hard-coded to its current books in the skill.

Define each canonical tag in `<KB>/catalog/aspects/<tag-id>.md` with type `Aspect`,
a stable `id`, `tag: <tag-id>`, title, description, scope boundaries, and aliases.
Link to source-local Aspect definitions and retain their terminology differences.
Canonical labels do not make different author meanings identical.
Reuse an existing meaning before creating another ID; create only useful entries supported by the selected sources.

## Content Before Words

Assign a tag only after reading the relevant passage with its necessary context.
Identify the mechanism, affected property, and stated conditions or limits.
The author's vocabulary may differ from the tag or may never name the property.
Additional disk writes can substantiate a performance cost; rejection of a stale lease holder's write can substantiate an integrity constraint.
These assignments require reading the mechanism and consequences, not detecting the words "performance" or "integrity".
Substantive relevance also includes definitions, measurement methods, prerequisites, and constraints; a passage need not improve the property to receive its tag.
For example, a correct clock choice can support a latency-measurement constraint while making no request faster.

The converse matters equally: a word in a heading, product description, citation,
or passing mention is insufficient evidence of a substantive aspect discussion.
Do not infer every theoretically possible benefit or risk of a technique.
Mark an indexer's interpretation with `inference: true`; do not turn a plausible interpretation into an author statement.

## Local Record Schema

For each local card, add:

```yaml
domains: [data-management]
tags: [performance]
aspect_relations:
  - tag: performance
    aspect: a01.md
    relation: cost
    statement: "Under the stated workload, retaining intermediate results adds disk I/O."
    evidence: ../text/chapter.md#u-materialization
    inference: true
```

This is a schema example, not a source claim. Use the source language for statements.

- `aspect` is a relative path to a source-local card with `type: Aspect`.
- `relation` is `definition`, `benefit`, `cost`, `constraint`, `trade-off`, or `concern`.
- `statement` states the substantive relevance or effect and its conditions/limits; do not invent a positive effect for a definition.
- `evidence` is a relative path plus explicit anchor to the actual source passage. Keep its original section/location visible in the linked text or the card's evidence prose.
- `inference` is true when the aspect connection is the indexer's interpretation.

`tags` must equal the deduplicated tag IDs in `aspect_relations`.
Every assigned tag needs a local Aspect and source evidence; a bare tag or link to an unqualified summary is insufficient.
An Aspect card may reference itself for its definition, but its evidence must lead to source text, not to itself.
Create a useful local Aspect definition when the needed concern lacks one; preserve existing IDs.

Use `tags: []` and `aspect_relations: []` when no substantive aspect relation is established.
Use `domains: []` for unresolved classification. Empty or missing metadata establishes no facet membership, never irrelevance; an explicit empty tag list can record a completed review with no justified aspect.
Revisit existing metadata when better evidence changes the interpretation.

## Scope and Projection

Classify each card locally. Never propagate all book domains or tags to every child.
A source's `domains` summarize its principal areas and are not an exhaustive boundary on its cards.
A source's `tags` summarize supported aspects found in its cards, not properties of every passage.
For source-level aspect relations use local paths such as `cards/a01.md` and `text/chapter.md#u-id`, with a representative grounded statement for each tag.

Flat catalog projections use the union of their linked local cards' values.
Semantic cores and extensions use only the grounded facets of their selected claims,
following [semantic deduplication](deduplication.md). A group's navigation can expose
facets of its members without implying that every property applies to its core.
Catalog entries link back to those cards for aspect relations and evidence; do not maintain an independent interpretation there.
Canonical Aspect entries additionally define the shared tag; their links show the source meanings behind it.
Use a canonical Aspect's singular `tag` field to identify the vocabulary entry. Its aggregate `tags` describe the linked cards and must not be mistaken for a claim that all those properties belong to the canonical definition itself.
Text files and individual units need no copied book-wide facet metadata: use the selected card's grounded relations and read the actual unit.

## Search Contract

Interpret the user's desired result, situation, constraints, and failure symptoms first.
Infer candidate domains and aspects from these meanings even when their labels are absent.
Treat them as hypotheses to check against source evidence.
For example, "some clients wait seconds although the average is fine" suggests tail response times without naming a performance tag.

Translate each hypothesis into mechanisms, consequences, task descriptions, aliases,
and alternative formulations. Search those and inspect candidate cards and enclosing passages.
Tags are fast routes to evidence, not proof of applicability; their absence is not proof of irrelevance.
Group matches by claim meaning and conditions before opening full local cards.
Different facets neither prove different meanings nor prove equivalence.
An extension can supply a relevant facet absent from its core; keep that route visible.

By default prioritize matching facets while retaining a search branch outside them,
including unclassified cards and adjacent subject areas. Apply hard facet restrictions only for the user's explicit scope.
Distinguish explicit scope from the system's interpretation of the request.
Asking about performance expresses an information need; it does not itself mean "exclude every card without a performance tag".
Distinguish an explicit subject/source restriction from an explicit metadata predicate such as "only cards tagged performance"; inspect unclassified material for content applicability unless the user specifically excludes it.
Multiple tags do not have to coexist in one card: separate cards may provide the relevant aspects of a solution, connected through evidence.
Do not manufacture a joint guarantee by combining unrelated passages.

A new application domain can reuse general mechanisms from another domain.
An index-rebuilding question about RAG can require data-management evidence even if no source has a `rag` domain.
Do not label general source passages with every possible future application to compensate for overly narrow search.

Return the mechanism, relevant aspect effects, conditions, limitations, and exact source links.
Explain cross-domain transfer as an indexer's application when the source did not discuss the user's application.
