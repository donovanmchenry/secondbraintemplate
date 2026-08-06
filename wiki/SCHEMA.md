# Wiki Schema

This file is the operating contract for Second Brain's long-term knowledge. The wiki
is a maintained, interlinked Markdown synthesis: update it incrementally instead of
reconstructing durable knowledge from raw material for every question.

The local `USER.md` is the canonical personal profile. Link to it when personal
context matters; do not duplicate personal facts in tracked wiki pages. Short-lived
priorities belong in local `NOW.md`, optional longer-lived tasks belong in local
`tasks/index.md`, and current project state belongs in `projects/` or its source
repository.

## Architecture and Ownership

1. `raw/` holds approved source records and origin notes. Retained sources are
   immutable evidence.
2. `pages/` holds maintained synthesis about durable subjects and relationships.
3. `index.md` is the discovery map. It links every durable page and summarizes its
   purpose in one line.
4. `inbox.md` queues evidence that has not yet been verified or synthesized.
5. `log.md` is the append-only chronological record of meaningful wiki operations.

Do not add vector search, embeddings, a database, or RAG unless the owner explicitly
chooses that complexity. Start at `index.md` and use ordinary Markdown links and text
search.

## Page Types

- **Workspace profile:** purpose, scope, boundaries, and routing for the second brain.
- **Entity:** a durable person, organization, system, place, or named subject.
- **Topic:** an enduring concept synthesized from multiple pieces of evidence.
- **Relationship:** a durable connection that does not fit cleanly on one entity
  page; otherwise describe it on the affected entity pages.
- **Decision:** a confirmed choice with its date, context, consequences, and sources.
- **Synthesis:** a durable comparison, analysis, or answer worth retaining.

Create a wiki page for project-related material only when it is durable cross-project
knowledge or the owner explicitly approves it. Project discovery and operational
status remain in `projects/` and the project source.

## Page and Link Rules

- Use lowercase kebab-case filenames under `pages/`.
- Give each durable subject one canonical page. Extend it instead of creating a
  competing page.
- Link the first useful mention of related subjects with relative Markdown links.
- Add every durable page to `index.md` in the same change; do not leave orphan pages.
- Prefer focused synthesis over an activity dump. Keep transient tasks, messages, and
  live service state in their owning systems.
- Use descriptive headings. Durable claims must make sense without chat history.
- Omit empty sections instead of inventing content.

Use this shape when helpful:

```markdown
# Page Title

## Summary

Current synthesis.

## Details

Durable facts, relationships, decisions, or implications.

## Open Questions

- Unresolved uncertainty, contradiction, or follow-up.

## Sources

- Source: `<relative path or stable URL>` — what it supports; accessed or confirmed
  YYYY-MM-DD when relevant.
```

## Sourcing and Claim State

- Every consequential durable claim needs traceable provenance: an immutable record
  in `raw/`, a canonical workspace file, a stable external URL, or explicit owner
  confirmation recorded with its date.
- Store imported source material under `raw/` only when retention is approved. Do not
  silently rewrite it after ingest; corrections become a new record or adjacent
  origin note that points to the original.
- A link alone is not synthesis. State what the source supports.
- Keep observation separate from inference. Label an inference and cite its evidence.
- Mark uncertain claims `Uncertain`, conflicting claims `Contradiction`, and claims
  needing revalidation `Stale`. Include the reason, sources, and next check when
  known. Never resolve a conflict by silently deleting one side.
- Never store secrets, credentials, private message bodies, or sensitive raw data.
- Because the repository is public by default, keep personal knowledge local unless
  the owner deliberately changes the repository to private and approves syncing it.

## Ingest Workflow

1. Confirm that the source may be retained and identify its provenance. If it cannot
   be copied, retain a stable pointer and access date.
2. Preserve approved source material under `raw/` without changing its substance, or
   link to a canonical workspace source that already remains unchanged.
3. Read `index.md` and only the smallest set of related pages.
4. Put unverified, ambiguous, or unsynthesized evidence in `inbox.md`. Ask before
   retaining sensitive or consequential claims.
5. Integrate confirmed evidence into the narrowest canonical page. Update every page
   whose claims or relationships materially change.
6. Expose contradictions, uncertainty, and stale claims with their provenance.
7. Refresh the page summary in `index.md`, check links, and append one ingest or
   update entry to `log.md`.
8. Review the diff for unsupported claims, personal-profile duplication,
   project-state leakage, and secrets.
9. Run `npm run validate` when Node.js is already available; otherwise inspect the
   same boundaries manually.

## Query Workflow

1. Read `index.md` first and follow only relevant links.
2. Read local `USER.md` only when personal context or preferences matter.
3. Verify consequential, uncertain, conflicting, or potentially stale claims against
   their sources.
4. Cite the local pages and sources used. Distinguish confirmed facts from inference
   and unresolved uncertainty.
5. If the answer creates durable synthesis, propose the narrowest useful update and
   apply it only within the owner's retention and sync boundaries.

Routine lookups do not need log entries. Log a query only when it produces durable
synthesis, exposes a material gap or contradiction, or changes the wiki.

## Lint Workflow

Review the wiki periodically for:

- durable pages missing from `index.md`, orphan pages, and broken relative links;
- duplicate canonical subjects or unclear page ownership;
- claims without provenance and source records that were silently altered;
- unresolved contradictions, unlabeled inference, and stale time-sensitive claims;
- related pages that disagree or were not updated together;
- recurring durable entities or relationships that lack a clear home;
- personal facts duplicated from `USER.md`, tasks or project state in the wiki,
  secrets, credentials, or sensitive account data;
- inbox items that should be synthesized, rejected, or retained with an explicit
  reason.

Append a `lint` entry to `log.md` with findings and changes. A clean pass should say
so.

## Inbox Format

```markdown
## YYYY-MM-DD — Short label

- Source: relative path, stable URL, or owner confirmation
- Status: unverified | ambiguous | awaiting synthesis | blocked
- Related pages: links or `none yet`
- Notes: what is known and what must be resolved
```

Remove an item only after it is synthesized, rejected, or superseded; record the
outcome in `log.md`.

## Log Format

Append entries beneath `## Changes`, oldest first:

```markdown
## [YYYY-MM-DD] action | Short title

- Sources: paths, URLs, owner confirmation, or `none`
- Pages: links to affected wiki pages
- Summary: what changed, what was learned, or what the lint found
```

Use one of `setup`, `ingest`, `update`, `query`, or `lint` for `action`. Do not edit or
reorder prior entries; append a correcting entry instead.
