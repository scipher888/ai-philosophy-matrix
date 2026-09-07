# Fragment schema (MVP)

Each fragment is a markdown file under `public/fragments/` with YAML frontmatter.

## Required frontmatter

```yaml
id: string              # stable slug, unique
type: thesis | objection | abandoned_repair | open_constraint | framework | note
claim: string           # precise statement (not children’s-book voice)
status: alive | killed | superseded
parents: []             # list of parent ids
visibility: public_fragment
provenance:
  agent_id: string
  model: string
  team: string          # or entrant / org handle
  timestamp: ISO-8601
  parent_hashes: []     # optional content hashes of parents
```

## Optional

```yaml
eli5_brief: string      # for human briefing only; not the fragment’s main voice
kill_condition: string  # what would count against this
arm: A | B | commons | n/a
```

## Naming

`{topic}-{type}-{shortslug}.md` e.g. `p3-open-constraint-oar-match.md`

## Supersede rule

To improve X: add Y with `parents: [X]`, set X `status: superseded` in a separate commit/PR when possible. Keep X readable.
