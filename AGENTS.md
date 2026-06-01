# Repository Instructions

## Goal

Preserve and publish Youngrok LEE's discographies as clean, machine-readable
Markdown while retaining source provenance and editorial context.

## Markdown Structure

- Publish from the `docs` directory for GitHub Pages.
- Use one directory per processed artist under `docs`, for example
  `docs/Friedrich Gulda/`.
- Put the artist discography in that directory as `index.md`, for example
  `docs/Friedrich Gulda/index.md`.
- Keep `docs/index.md` as the public landing page with a short explanation and
  links to all processed discographies.
- Do not include local filesystem paths in public compiled pages.
- Do not add source-path metadata headers such as `Source:` or `Wrapper page:`
  to compiled artist pages unless explicitly requested.
- Add a composer index near the top, before the discography sections.
- Split discography tables by composer using level-2 headings, for example
  `## Beethoven`.
- Each work starts with a level-3 heading, for example `### Piano Sonata
  No. 1 in F minor, Op. 2 No. 1`.
- If level-3 headings become unsupported in a target renderer, use bold work
  titles as a fallback.
- Use one recording table per work heading.
- Recording variants follow the work heading as normal rows in that work's
  table.
- Keep the table schema identical across composer sections.
- Keep rows machine-readable: one logical recording event per row.
- Do not add generated explanatory sections, process notes, extraction counts,
  or commentary to compiled discography pages.
- Compiled discography pages are for preserving original content and meaningful
  source notes only. Put project-level explanations on `docs/index.md`,
  `README.md`, or `AGENTS.md`, not in artist discographies.

## Composer Index

- Group composers by starting letter.
- Use one line per starting letter.
- Link composer names to their level-2 composer sections.
- Separate names with ` - `.
- Use the display spelling from the normalized composer heading.
- If there is only one composer for a letter, still write the letter line.

Example:

```markdown
A: [Albéniz](#albéniz)

B: [Bach](#bach) - [Beethoven](#beethoven) - [Brahms](#brahms)
```

## Table Schema

Use this table schema unless a source requires an explicitly documented
exception:

| column | purpose |
| --- | --- |
| blank first column | Source recording variant number. |
| `recording` | Date, venue, live/studio status, and other event-level details. |
| `details` | Grouped contextual details: `**With**:`, producer/engineer data, transfer/remastering credit, and notes. |
| `releases` | Grouped release/media information using bold labels such as `**78s**:`, `**LP**:`, `**CD**:`, `**Tape**:`, and `**Other**:`. |

Use this compact header row:

```markdown
|  | recording | details | releases |
| --- | --- | --- | --- |
```

Do not include a `composer` column inside composer tables. The composer is
supplied by the level-2 heading.

Example:

```markdown
## Beethoven

|  | recording | details | releases |
| --- | --- | --- | --- |
| <a id="beethoven-piano-sonata-no-1-op-2-no-1-rec-1"></a>1 | 15,16 Mar. 1948, Wolfbach Studio, Zürich | Producer/Engineer ; Walter Legge/? | **LP**: ...<br>**CD**: ... |
```

## Anchors

- Composer anchors come from `## Composer` headings.
- Work anchors come from `###` work headings, using raw HTML when a stable
  custom anchor is needed.
- Composer and work headings should include a visible leading paragraph-sign
  permalink, for example `[¶](#beethoven) Beethoven`.
- Recording anchors use raw HTML before the recording number.
- Anchor IDs should be stable lowercase ASCII slugs.
- Do not derive anchors from catalog or release data, because those can change
  or be normalized later.

Example IDs:

```text
beethoven-piano-sonata-no-1-op-2-no-1
beethoven-piano-sonata-no-1-op-2-no-1-rec-1
```

## Producer And Engineer Credits

- Preserve original producer/engineer syntax.
- Do not normalize `?` to `unknown`.
- Use source forms such as `Producer/Engineer ; Gottfried Kraus/?`.
- Preserve mono/stereo distinctions when present.

Examples:

```text
Producer/Engineer ; Gottfried Kraus/?
Producer/Engineer ; James Walker/Gil Went(monaural), James Brown(stereo)
```

## Editorial Normalization

- Use `Op. 3`, not `op.3`, `op. 3`, or `Op.3`, in normalized table text.
- Use `No. 3`, not `No.3`.
- Preserve catalog numbers as written unless a normalization rule has been
  explicitly agreed.
- Preserve source wording in notes when it affects meaning.
- Do not silently resolve uncertain source data. Keep uncertainty visible in the
  relevant field or `notes`.
- Keep artist and contributor names as the source gives them unless a clear
  normalization rule exists.

## Typography

- Follow common English typography and The Chicago Manual of Style where it is
  applicable to normalized text.
- Use one space after commas, semicolons, colons, and sentence-ending periods.
- Do not put a space before commas, semicolons, colons, periods, or closing
  parentheses.
- Put one space before an opening parenthesis and no space immediately after it,
  unless the parenthesis is part of a catalog number or source catalog syntax
  where the original spacing is meaningful.
- Do not put spaces just inside square brackets in editorial notes:
  `[originally Amadeo]`, not `[ originally Amadeo ]`.
- Normalize repeated whitespace to a single space in prose and table cells.
- Preserve source catalog numbers and label identifiers when spacing appears to
  be part of the identifier.
- Use nonbreaking spaces where a line break would harm readability or meaning,
  especially in compact musical/catalog references.
- Prefer nonbreaking spaces in normalized text for:
  - `Op. 3`
  - `No. 3`
  - `K. 466`
  - `BWV 846`
  - `D. 845`
  - `Hob. XVI:52`
  - initials and short name prefixes such as `J. S. Bach`, `W. A. Mozart`, and
    `F. J. Haydn`
- Do not insert nonbreaking spaces inside raw catalog identifiers if doing so
  could make copy/paste or lookup less reliable.
- Normalize source note markers such as `Note ]` and `NB ]` to `**Note**:`.
- Use `**Notes**:` only when combining multiple note sentences under one label.

## Source Preservation

Each artist file should preserve or summarize public source context when useful:

- Original page title.
- Original created date and last update date when available.
- Introductory caveats and scope notes.
- Acknowledgements, contribution notes, bibliography/source lists, and footer
  notes.
- Links worth migrating, especially jacket-image links and source references.
- Rights notice and contact spelling.

Never preserve private local filesystem paths in public content.

Do not add a separate generated "Other Source Material Worth Preserving" section
to artist pages. Integrate preserved source caveats, acknowledgements, resources,
footer notes, and rights notices as content, without commentary about the
compilation process.

## Rights Notice

Use the repository rights notice style:

```text
Copyright © 1999–present, Youngrok LEE.

Links are welcome, but please get approval from Youngrok LEE before reusing,
copying, or quoting these materials.

Contact: youngrok.lee_at_gmail.com
```

Preserve the contact spelling exactly as `youngrok.lee_at_gmail.com`.
