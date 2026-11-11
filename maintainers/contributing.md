---
description: Keep the handbook practical, source-grounded, and consistent as FastDyn evolves.
---

# Contribute to the handbook

A useful contribution helps a reader complete an experiment or understand an important contract. Explain the question, the required setup, the action, the observable result, and the implementation boundary. Prefer one complete example over a list of features with no working path between them.

## Choose the right chapter

User workflows belong in getting started, instrumentation, devices, simulation, and analysis. API and extension contracts belong in extending and reference. Architectural explanations should identify component responsibilities and show how a decision affects execution. Proposals belong in designs until the corresponding interface is implemented and has a demonstrated workflow.

Use the [source map](../reference/source-map.md) before adding a new page. It helps avoid creating a second explanation of an API that already has a natural home.

## Ground the claims

Read the current implementation and relevant tests, not only an older README. Add a short source guide with pinned links to the files that establish the chapter's contract. Use tests as evidence of what is asserted, and distinguish the existence of a test from a test result observed during the documentation change.

For a branch-only feature, name the branch, pin the revision, and state the prerequisites and validation level. For a proposal, describe intended semantics and the existing foundations without presenting an invented API as current functionality.

If code and earlier documentation disagree, document the behavior the inspected implementation provides and keep the explanation useful to the reader. A handbook chapter should not become an unrelated backlog of every issue found during inspection.

## Write examples that can be followed

State the working directory, required build options, firmware fixture, and expected output. Use the public CLI or API that the feature actually supports. Configuration fragments should identify the existing table they extend and any required surrounding configuration.

Do not transplant literal addresses into a different firmware image. Explain when symbol resolution, instruction validation, or layout checks must run again. Keep architecture-specific register and ABI assumptions explicit.

For source-code contributors, follow FastDyn's [coding conventions](https://github.com/boardrunner2049/FastDyn/blob/f9666d7f518c373e89831d8e14a6371a27fe6436/docs/CodingConventions.md). In particular, retain feature ownership: plugin policy stays with the plugin, reusable immutable facts can move into host analysis, and downstream orchestration stays with the downstream project.

## Explain fidelity and performance precisely

Describe the firmware boundary an experiment exercises. A sensor-publication hook, a peripheral register model, and hardware passthrough each answer different questions. State the actual input representation, time policy, and modeled state when they matter to the result.

A performance claim needs a baseline, completion condition, configuration, raw measurements, and a statement of the behavior preserved. Avoid universal speed, fidelity, architecture, or losslessness claims based on one configuration.

## Keep navigation and terminology consistent

Use one H1 per page and concise section headings. Add pages to `SUMMARY.md` exactly once. Use relative links between book pages and pinned links to implementation sources. Add a term to the [glossary](../reference/glossary.md) when several chapters need the same definition.

Use diagrams when they explain a boundary, feedback loop, or branching workflow more clearly than prose. Keep each diagram focused; supporting details belong in the surrounding text. Tables work well for configuration fields, API mappings, and support differences.

Before committing, check frontmatter, local links and anchors, fenced-code syntax, source paths, and the configuration files. For runtime examples, state whether they were run and with which build. A docs-only syntax check is useful evidence, but it is not a firmware integration test.
