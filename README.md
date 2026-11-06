# Molecule

**Intellectual indexing and meaningful connection discovery for Obsidian.**

Molecule helps you explore *what your notes are saying*—not just which words, tags, or folders they share. It describes ideas within notes, organizes those descriptions into browsable indexes, and looks for substantive relationships between notes that might otherwise remain unnoticed.

> **Development status: Current Working Beta — v0.5.241**  
> v0.5.241 is the current actively used working build. Several newer features and fixes have been tested in actual vault use, but the complete build has not undergone exhaustive regression testing or clean-install validation. v0.5.232 remains the formally accepted reference baseline. Neither designation implies that every feature has been independently verified.

## What Molecule does

- **Layer A — Describe ideas.** Save a note's Core Idea, Other Major Ideas, topics, and themes/concepts. Descriptions can be entered or refined manually, or generated using optional AI analysis.
- **Layer B — Discover connections.** Retrieve promising note candidates through local semantic search, then optionally use AI to evaluate whether they have an intellectually meaningful relationship and classify that relationship. Similar wording alone is not sufficient.
- **Intellectual Index.** Browse and navigate saved Topics and Themes & Concepts across your notes.
- **Core Idea Export.** Create a separate Markdown inventory of saved Core Ideas, scoped by folder, folder with subfolders, or filename range. Optionally include Other Major Ideas. Entries link back to their original notes; missing Core Ideas are identified explicitly.
- **Scripture reference catalog (optional).** Locally record, browse, and compare Scripture references associated with notes. This is separate from semantic connection discovery.
- **Comparison notes and review tools.** Review descriptions and relationships and, when requested, generate new Markdown notes collecting selected connections.

Molecule is designed to minimize routine manual classification while leaving room for human correction and judgment.

## Getting started

Molecule currently targets **Obsidian desktop** (minimum Obsidian version **1.5.0**).

1. Install the complete plugin package in your vault's `.obsidian/plugins/molecule/` directory and enable **Molecule** under Obsidian's Community plugins settings. Keep the package's `runtime/` dependencies intact.
2. In Molecule's settings, choose the indexing scope and any exclusions.
3. **Run local indexing** to register eligible notes. Indexing is local and does not call an AI API.
4. For semantic candidate retrieval, build **local semantic coverage (vectors)** using Molecule's free coverage tools. Registration and vector generation are separate steps.
5. Optionally configure an **OpenAI API key** to generate Layer A descriptions or run AI-assisted Layer B relationship evaluation. API use is billed separately from ChatGPT subscriptions.
6. Start with a small group of familiar notes, inspect their descriptions, and then try connection discovery on a focus note.

You can use local indexing, manually saved descriptions, and other local features without paying for AI processing. AI-powered workflows should be previewed on small selections before running large jobs.

## Protecting your notes and plugin data

Molecule's normal indexing, analysis, and discovery workflows **do not rewrite existing Markdown notes**. Explicit export and comparison-note commands create new files under user control.

Before upgrading an existing installation, back up your vault and the **entire** `.obsidian/plugins/molecule/` directory. In particular, **do not delete or overwrite `data.json` or other locally generated state, caches, ledgers, or job files** when replacing distributed plugin files.

## Versions and releases

| Version | Status | Notes |
| --- | --- | --- |
| **0.5.241** | **Current Working Beta** | Actively used; includes the Core Idea Export feature, the tested candidate-browser scrolling correction, and export-scope wording refinement. Full regression coverage remains incomplete. |
| **0.5.232** | **Accepted reference baseline** | Earlier formally accepted build, retained for comparison and rollback. |

The term *beta* means Molecule is usable and under active development; it is **not** a claim that every feature is production-certified. Newer builds should be tested incrementally, with data backups and attention to regressions.

## Documentation

See the **Molecule User Guide** for the full setup sequence, settings, Layer A and Layer B workflows, the Intellectual Index, optional features, and glossary. Add a link here once the guide has been uploaded to this repository.

## Availability and licensing

Molecule's plugin code includes an MIT license in its distribution package. The complete installation also includes third-party runtime components and model assets with separate license and redistribution considerations; see `THIRD_PARTY_LICENSES.md` and the `licenses/` directory in the package. **Third-party redistribution clearance and a clean-install test should be confirmed before publishing a complete installation package publicly.**

## Feedback and development

Molecule is an evolving project. Reports are most useful when they include the plugin version, what was expected, what happened, and whether the issue is reproducible. For connection quality, meaningful matches, missed relationships, false positives, and incorrect relationship classifications are all valuable evidence.
