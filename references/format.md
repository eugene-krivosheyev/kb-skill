# Data Format

Use Open Knowledge Format (OKF) version 0.2.
The [OKF specification](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/main/SPEC.md) defines the format.
The rules below define the KB profile.
The profile adds search guidance. It does not change OKF.
Use these local rules without a network request during normal work.

## Objects

| Object | Meaning |
| --- | --- |
| Source | One book, paper, manual, or other work, with a specified edition or version. |
| Unit | A passage with a stable ID and a location in the source. |
| Concept | A meaning, principle, model, rule, or distinction. |
| Task | A problem or desired result. |
| Solution | A method that addresses a task under specified conditions. |
| Aspect | A concern that applies across subjects, such as performance, safety, reliability, or cost. |
| Domain | An indexer's subject-area classification used to navigate and prioritize relevant material. |
| Card | A short record that describes an object and links to evidence. |
| Catalog | Entries that connect cards across sources. |

A pattern, algorithm, procedure, or practice can be a solution.
Keep a more specific source term when it helps selection.
Do not force each concept into a solution form.

## Layout

```text
<KB>/
  index.md
  domains/
    index.md
    <domain-id>.md
  sources/
    index.md
    <source-id>/
      index.md
      source.md
      original/
        <original-file>
      text/
        index.md
        <part>.md
      cards/
        index.md
        <card-id>.md
  catalog/
    index.md
    <view>/
      index.md
      <entry-id>.md
```

`<KB>` is the external root selected by the command, or `~/kb` by default.
Keep one shared root index, source list, and catalog for that KB.
Use `concepts`, `tasks`, `solutions`, or `aspects` for `<view>`.
Keep the domain vocabulary in `domains/`. Define canonical tag meanings in catalog Aspect records with a `tag` field.
Create directories only when they contain useful entries.
Keep all source material and local links within its source directory.
Store catalog entries outside source directories.
Each source package must remain useful without the catalog.

## OKF Files

- Give each ordinary Markdown file YAML frontmatter with a non-empty `type`.
- Add a `title` and a one-sentence `description` to each KB record.
- Use descriptive types, such as `Source`, `Source Text`, `Concept`, `Task`, `Solution`, and `Aspect`.
- Use `index.md` only for a list of links with short descriptions.
- Keep directory entries complete at each level.
- Keep source text entries in source order.
- Omit frontmatter from indexes, except for `okf_version: "0.2"` in the base root index.
- If you use `log.md`, group changes under ISO dates, newest first.
- Use relative Markdown links within each source package.
- Use exact file paths and explicit anchors for unit links.
- Use a literal anchor, such as `<a id="u-001"></a>`, for each unit.
- Keep unit IDs unique within their source.
- Keep existing IDs and anchors when their content is unchanged.

## Source Record

Record the source identity, edition, origin, and language in `source.md`.
Use `sources` entries with a `resource` to identify original material.
Point a source entry to the retained original file.
Record its original filename and local path.
Keep original page or section locations when available.
Do not invent page numbers.

Keep a coverage list in `source.md`.
Map each source section to its stored text or to an explicit gap.
For each gap, record its location and whether it is unread or unavailable.
Record the next unread location during a partial import.
Use the profile field `coverage: partial` or `coverage: complete`.
Use `complete` only after you check every source section.
Keep OKF `status` separate from import coverage.
Do not add a verification event for a simple index check.

## Original Files

Keep one unchanged original file per source package in `original/`.
Keep an EPUB file as `.epub`, without an additional `.zip` copy.
Readable text in `text/` is a separate representation, not another archive.
For a Markdown original, append `.original` to its filename.
Keep its bytes unchanged. This suffix prevents its use as an OKF concept file.
Keep only required extracted assets, such as referenced figures, within the source package.
Remove temporary archive copies and extraction files made by the current import after their use.
Do not remove pre-existing user files as duplicates.

## Source Text

Store the readable source text once, in natural sections.
Give each search unit a stable anchor within that text.
Keep the unit's original location with its anchor.
Use smaller sections within long chapters.
Keep code, equations, figures, tables, captions, and notes with their necessary context.
Record content that cannot be read as a gap.
Keep index descriptions separate from source text.

## Cards and Links

Use one card per useful concept, task, solution, or aspect.
Add a stable `id` to each card.
Use `aliases` for alternative names and `questions` for answerable user formulations.
Give indexed sources and local cards explicit `domains`, `tags`, and `aspect_relations`.
These fields, the catalog Aspect `tag` field, and `coverage` are KB extensions.
Follow [the facet model](facets.md) for their semantics, evidence, and empty values.

For each evidence link, state its role and original source location.
Useful roles include definition, problem, method, example, condition, limit, and consequence.
Link required definitions and related source passages.
Link solutions to tasks, conditions, alternatives, and consequences when the source supports these links.
State the relation in prose beside the link.

For each aspect relation, record its effect, conditions, and evidence.
Possible effects include benefit, cost, constraint, and trade-off.
Mark an indexer's interpretation as an inference.
Do not copy parent tags to all child units without evidence.

Use the same aspect names across sources where the meanings agree.
Keep narrower aspects when useful, such as latency and throughput within performance.
Keep distinct meanings separate, even when their names match.
Distinguish equal meanings, related meanings, broader meanings, and alternatives.

## Catalog

Link each catalog entry to the applicable local cards.
Derive its `domains` and `tags` from those cards; keep evidence-bearing aspect relations local.
Do not copy local relative paths verbatim into a catalog record.
Keep source-specific meanings and conditions visible.
Keep edition differences and disagreements explicit.
Do not replace local evidence with a combined summary.
Use stable IDs. Do not reuse an ID for a different object.
