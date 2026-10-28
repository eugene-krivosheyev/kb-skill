# Semantic Deduplication

## Purpose and boundary

Store one shared explanation of an equivalent meaning, distinct contributions in
`extensions/`, and equivalent witnesses in `confirmations.md`. Reduce repeated
reads before loading full source accounts. Preserve complete source-local cards,
original text, attribution, editions, anchors and source coverage.

Similarity generates candidates; equivalence requires reading the claim and its
conditions. Deduplicate propositions, not whole files, titles, people or topics.
A smaller index is useful only if the answer-changing information survives.
Keep selectors and records concise: avoid copying source prose into description,
metadata and body repeatedly, or adding unconditional dependencies for unrelated
questions. A small group may cost more context than its few original cards;
measure actual selected reads and report overhead rather than promising savings.

## Compare meanings

Compare the intended question, object, mechanism, result, preconditions, scope,
failure model, negation, quantifiers, units, thresholds and version. Preserve
whether a link is an author's statement or an indexer's inference.

- Equivalent claim with the same conditions: add a confirmation of that exact
  claim; do not create another shared explanation or extension.
- Partial overlap: confirm only the shared claims and retain the distinct parts
  as extensions or separate meanings. One matching sentence does not confirm
  an entire card, algorithm or core.
- Qualification, boundary, new consequence or counterargument: create/reuse the
  corresponding extension with explicit applicability and claim target.
- Different mechanism, incompatible definition, or independently usable alternative:
  use a separate core and cross-link it; a short alternative extension may route
  to that core. A task and its solution are related, not equivalent.
- Uncertain comparison or unavailable evidence: keep a distinct/uncertain route.
  Do not treat missing metadata, bibliography, or a shared citation as confirmation.

Different wording/language can express the same meaning; identical names can mean
different things. Organizational delivery time is not API latency. A local commit
is not an end-to-end processing guarantee. A numerical threshold with a changed
operator is not an equivalent rule. These comparisons apply to mechanisms and
conditions, not just these examples. Pairwise similarity is not transitive:
compare every contribution directly with its target claim.

## Shared layout and records

Use `catalog/<view>/<meaning-id>/`, where view is concepts, tasks, solutions or
aspects. Route cross-source discovery through `catalog/<view>/by-meaning/index.md`.
Keep existing source projections, source views and canonical tag nodes reachable.

- `index.md`: links with compact descriptions of the core's scope and each
  extension's applicability, kind and mandatory status. Include useful alternative
  terms and safe witness routes without listing every repeated account.
- `core.md`: one source-grounded explanation, necessary assumptions, stable claim
  anchors, baseline provenance, and exact primary support for each claim.
- `extensions/<extension-id>.md`: one distinct contribution, its target claim,
  applicability, consequence, support and inference status. Group by contribution,
  not by source: repeated descriptions of the same limitation share one extension.
- `confirmations.md`: equivalent witnesses for specific core or extension claims,
  with source/edition, local card and exact original passage. No repeated narrative.
  If large, use a compact selector and linked confirmation parts.

All ordinary records have type, stable id, title and description. Cores use the
object's normal type and `role: semantic-core`. Extensions use
`type: Semantic Extension`, `role: extension`, and `extension_kind`:
clarification, limitation, extension, counterargument or alternative.
Confirmations use `type: Evidence Set` and `role: confirmations`.
All share `semantic_group: <stable-group-id>`.

Cores additionally record `baseline_source`, `baseline_commit` when known,
`domains`, `tags`, and `required_extensions` (empty when none).
Extensions record `target` (relative link to an explicit claim anchor),
`applicability` (a usable condition), `domains`, `tags`, and
`required_extensions` for any further mandatory dependency.
Each required dependency records `path` (a relative record/claim link) and `when`
(`always` or an explicit trigger on the question/selected claim). For example:

```yaml
required_extensions:
  - path: extensions/organizational-policy.md
    when: always
  - path: extensions/visibility.md
    when: "When answering about consumer visibility or a delivery-delay bound."
```

Legacy plain-link entries mean `when: always`. Do not encode a conditional
requirement as an unconditional plain link or rely on prose to contradict that
field. Resolve selected dependencies transitively. A known false trigger does not
require loading that extension; an unknown material trigger requires inspection
or a conditionally scoped answer.
Use literal anchors for shared claims, for example `<a id="c-retry"></a>`.

Core and extension `support` entries bind one selected claim to actual evidence:

```yaml
support:
  - claim: "#c-retry"
    source: source-id
    card: ../../../sources/source-id/cards/retry.md
    evidence: ../../../sources/source-id/text/chapter.md#u-retry
    inference: false
```

Paths are relative to the containing file; an extension is one level deeper.
The source ID must agree with the linked package. `inference` retains the
original inference status; a shared interpretation never becomes an author claim.
A support entry covers only its claim under its stated conditions.
Confirmations use the same fields, but `claim` targets `core.md#...` or
`extensions/<id>.md#...`. Match on that claim and its conditions, not the whole
target record. Mere citation, copied wording, or another edition of the same work
does not establish independent empirical confirmation.

Do not copy every supporting source into core frontmatter. Keep one sufficient
primary witness per selected equivalent claim and route further witnesses through
confirmations. Prefer a readable, admissible witness for the current question;
the historical baseline need not be the best witness.

## Essential conditions and disagreements

Keep assumptions necessary to make the core true in the core's scope itself.
Use required extensions for further details that must accompany a selected claim.
Expose their triggers in the compact index and record the same triggers in
`required_extensions`; applicable dependencies cannot be omitted to save context.

A counterargument under the same applicable conditions is required when presenting
the contested claim. State attribution and disagreement; do not silently rewrite
the oldest statement as consensus, use majority voting, or let ten repetitions
outweigh one material counterexample. Different assumptions may explain apparent
disagreement; retain the conditional alternatives.

Keep extension targets direct and the required-dependency graph acyclic. Do not
make a chain of later books that requires reading all predecessors. Unknown
applicability requires inspection or an explicitly conditional answer.

## Chronology and indexing

For a new group use the earliest indexed source that actually contains the meaning,
according to the KB's Git introduction history. Use source introduction order,
not book publication year, commit author date or the most recently modified file.
For a tie, preserve recorded source-index order, then stable source ID.
Record known baseline provenance without inventing unavailable Git history;
when chronology is unavailable, state the fallback order used.

The first source in the KB is not the baseline for meanings it never discusses.
Chronology selects a stable starting explanation, not authority or truth.
Later evidence can require qualifications, disagreement or a separately named
meaning while baseline attribution remains visible.

Before a new shared entry, inspect compact candidate groups and necessary source
passages. Compare all relevant claim parts; add only genuinely new shared content.
Update aliases, extension selection descriptions and witness links so a later
question can find the new contribution without rereading all source accounts.

When reindexing an existing KB, process the requested sources in this introduction
order and preserve source-local originals/cards/anchors and their coverage. Keep
legacy projections usable. Track unmigrated sources/claims and unresolved matches;
semantic migration is complete only for the scope actually reconciled. Do not
declare a metadata grouping pass a rereading of the books.

## Facets

Local domains/tags and their evidence-bearing Aspect relations remain authoritative.
A core or extension projects facets only from local relations that substantiate
its selected claims; the rest of a supporting card does not transfer automatically.
Keep facet-to-claim provenance visible beside the relevant support or statement.

An extension may introduce a relevant domain or tag absent from the core. Expose
that route in group and by-meaning navigation; never filter it out just because
the core is untagged or has another facet. Group membership itself is not evidence
of every member's properties. Canonical tag definitions retain their existing
meaning and aggregate source-local facet model.

## Search before reading repetitions

Read compact selectors, then one relevant core and the applicable unique extensions.
Required restrictions, counterarguments and dependencies are part of the evidence
budget, not optional diversity. Follow original passages for the selected claims;
the shared core is a retrieval aid, not a substitute for source verification.

Do not load confirmations or every local account by default. Expand witnesses for
explicit comparisons, requested attribution/all-source lists, missing or weak
support, disputed claims, differing conditions, or a source/edition restriction.
For explicit source scope choose evidence from that scope: an outside baseline is
only navigation. A later source's support of one extension does not confirm the
whole baseline. Honor explicit metadata predicates at the claim's evidence route;
necessary context must not be falsely presented as matching that predicate.

Prefer additional candidates that supply a missing mechanism, condition, facet or
counterexample over another equivalent explanation. Do not suppress distinct
meanings just because their titles or wording overlap. Preserve adjacent-domain
and untagged fallback. In an unmigrated area use bounded legacy search, verify
equivalence as needed, and state uncertainty; never treat an incomplete registry
as a complete list of meanings.

A final compact answer does not remove earlier reads from the conversation.
Measure read selection in fresh search runs, not just the size of the final answer.
Do not promise a fixed context saving or count navigational summaries as original
evidence. Source coverage limitations remain material after deduplication.

## Behavioral checks

Use isolated fixtures or a read-only representative KB subset. Evaluate indexing
decisions and search reads/answers, not just the presence of these headings.
Include repeated paraphrases; same-name different meanings; partial overlaps;
same-scope contradiction versus changed assumptions; mandatory restrictions;
extension-only facets and untagged cores; explicit source/edition predicates;
legacy/unmigrated candidates; inference status; unreadable support; and a request
for all confirming sources.

Check that evidence remains attached to the right claim and edition, no novel
conditions disappear, and equivalence introduces neither inherited guarantees
nor dependency cycles. Compare actual selected record/passage reads with the
duplicated baseline using measured bytes/words or available token counts.
Report fixture scope, regressions, unresolved failures and the limits of measured
savings; a synthetic pass is not a full audit of the live KB.
