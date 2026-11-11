---
description: Maintain the existing GitBook site mapping and publish this repository as one coherent handbook.
---

# Publish and maintain the book

This repository is the GitBook source for FastDyn. Its site configuration already maps the repository root to the default `fastdyn` space. Chapters live in topic directories, and `SUMMARY.md` defines their reading order.

## Configuration in this repository

| File | Purpose |
| --- | --- |
| `gitbook-docs.yaml` | Site title and the stable mapping from the `fastdyn` space to `./` |
| `.gitbook.yaml` | This space's content root, first page, and navigation file |
| `README.md` | Handbook landing page |
| `SUMMARY.md` | Chapter navigation and page groups |

The topic directories are chapter groups inside one space. They are not separate GitBook spaces or site sections. This keeps cross-chapter links local and preserves the identity established by the original site configuration.

## Connect Git Sync

Select `Arslan8/FastDyn-Book`, branch `main`, with the repository root as the project directory. Import the repository's content into the mapped space. The space configuration selects `README.md` and `SUMMARY.md`.

The site's `path: docs` is a navigation path; its `content.directory: ./` is the repository location. Do not create a `docs/` directory merely to make those two strings look alike. Keep the stable space key `fastdyn` unchanged when renaming the display title or adjusting presentation.

These meanings follow GitBook's [site schema](https://api.gitbook.com/gitbook-docs.yaml) and [Git Sync configuration documentation](https://gitbook.com/docs/docs-as-code/git-sync/content-configuration).

## Updating a chapter

Edit the chapter's Markdown file and its source links together. Keep examples tied to a stated source revision, and explain any newer branch-specific behavior. Update the capability status page when an extension moves from proposed work into an implemented and documented interface.

When adding a page, add it to `SUMMARY.md` once, check its local links, and verify its title and description. When moving a page, update links that refer to the old path and consider the public URL implications before removing the old location.

Run examples from the stated working directory. Make clear whether a command is executable after the listed prerequisites, a configuration fragment, or a conceptual design sketch. Record the validation actually performed rather than inheriting a claim from a neighboring page.

## Review the rendered result

After Git Sync imports a change, inspect the landing page, navigation groups, code blocks, tables, and diagrams in GitBook. Check a cross-chapter link and a pinned source link. Verify that the imported pages belong to the existing space and that an unchanged chapter did not acquire a duplicate page.

A successful Git commit establishes the source revision. It is separate from confirmation that the GitBook service imported and published that revision. Keep those outcomes distinct in release notes.

## Updating the source baseline

The main baseline for this edition is `f9666d7f518c373e89831d8e14a6371a27fe6436`. A baseline update should review the public APIs, configuration parser, build defaults, shipped examples, and tests before replacing source-link SHAs in bulk.

Keep branch-preview evidence pinned to the revision that was inspected. When a branch is merged, check the resulting main implementation instead of assuming the earlier branch text is still exact. The [source map](../reference/source-map.md) identifies the original documentation and code locations behind each chapter.
