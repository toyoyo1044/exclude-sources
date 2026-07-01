---
name: exclude-sources
description: Apply and maintain configurable technical information-source exclusions and source-priority policies. Use when researching, debugging, implementing, designing, reviewing, or explaining technical topics, and when updating source inclusion or exclusion rules for technical work.
---

# Technical Source Policy

## Purpose

Apply durable source exclusions and source-quality rules during technical work. Treat every active policy entry as a mandatory constraint.

## Operating Rules

- Follow every active entry in `Policy Entries`.
- Do not open, summarize, cite, or rely on an excluded source.
- Ignore excluded sources in search results and continue with other sources.
- Add each relevant `Search exclusions` value when the search tool supports exclusions.
- Prefer primary and official sources. Use secondary sources only when preferred sources do not answer the practical question.
- If sufficient evidence cannot be found without excluded sources, state that no primary or trustworthy source was found and do not use the excluded sources.

## Source Priority

Prefer sources in this order:

1. Official documentation
2. Official GitHub repositories
3. RFCs, specifications, and standards
4. Official issues and discussions
5. Maintainer blogs and release notes
6. Trustworthy company engineering blogs
7. Stack Overflow only as a supplemental source for practical troubleshooting

## Policy Entries

### Excluded Technical Article Platforms

Status: active

Scope: technical research, debugging, implementation, design, review, and explanation.

Targets:

- Qiita
- Zenn

Excluded domains:

- `qiita.com`
- `*.qiita.com`
- `zenn.dev`
- `*.zenn.dev`

Search exclusions:

```text
-site:qiita.com -site:zenn.dev
```

Required behavior:

- Do not open pages from the listed targets.
- Do not summarize articles from the listed targets.
- Do not cite the listed targets.
- Do not use content from the listed targets as evidence or as the basis for implementation decisions.
- Ignore results from the listed targets and find another source.

## Updating This Skill

When adding or changing an information-source policy:

1. Keep the frontmatter `description` generic and broad enough to trigger for technical research and source-policy maintenance.
2. Add or update an entry under `Policy Entries` using `Status`, `Scope`, `Targets`, `Excluded domains`, `Search exclusions`, and `Required behavior`.
3. When adding a site or service to an existing entry, update `Targets`, `Excluded domains`, and `Search exclusions`. Change `Required behavior` only when the behavior itself changes.
4. List both the bare domain and wildcard subdomains when the rule covers both, such as `example.com` and `*.example.com`.
5. Keep search exclusions copyable as one `text` block. Add one `-site:<domain>` exclusion for each searchable bare domain.
6. Update `Source Priority` only when the general ranking changes for every policy.
7. Update `agents/openai.yaml` only when its generic user-facing metadata or default prompt becomes stale.
