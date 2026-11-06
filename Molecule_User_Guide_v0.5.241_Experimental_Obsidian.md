---
title: Molecule — User Guide
plugin: Molecule
version: 0.5.241
type: user-guide
updated: 2026-11-06
tags:
  - molecule
  - obsidian
  - documentation
---

# Molecule — User Guide

> [!info] About this guide
> This guide describes **Molecule v0.5.241** for Obsidian. It follows the normal panel and Settings screen from top to bottom, then explains the everyday workflow and optional features. Button and setting names reflect this version; features marked *optional* can be ignored during ordinary use.

## Contents

- [[#1. What Molecule is for]]
- [[#2. The Molecule panel, top to bottom]]
- [[#3. Settings, top to bottom]]
- [[#4. A normal start-to-finish workflow]]
- [[#5. Working offline or without paid AI]]
- [[#6. The full-vault cost estimator]]
- [[#7. The Layer A review tools]]
- [[#8. The Intellectual Index]]
- [[#9. Optional feature — Principles]]
- [[#10. Optional feature — Scripture Reference Catalog]]
- [[#11. Optional feature — Diagnostics and development tools]]
- [[#12. Optional feature — Exporting Core Ideas]]
- [[#13. Safety, costs, and common questions]]
- [[#Glossary]]

---

## 1. What Molecule is for

Molecule is an Obsidian plugin designed to **index the ideas in your notes and discover intellectually meaningful relationships among them**.

Ordinary Obsidian links show relationships someone has already noticed and recorded. Tags and folders group material by subject. Molecule adds a different layer: it tries to understand **what a note is actually saying**, then find other notes that support, develop, qualify, illustrate, apply, or challenge that idea—even when they do not use the same words or belong to the same topic.

Its primary workflow has two stages:

1. **Description (Layer A):** Create a structured intellectual description of a note: its central claim or information, optional other major ideas, topics, and themes/concepts.
2. **Connection discovery (Layer B):** Search the vault locally for plausible related notes, then use an AI evaluation step to decide which pairs have a substantive relationship and what kind of relationship it is.

The local search stage identifies **candidates**, not proven connections. The second stage evaluates them. A shared keyword, tag, or broad topic is not enough by itself to constitute a connection.

Molecule can also collect these results into a **new comparison note**, with Obsidian embeds of the connected notes organized by relationship type.

> [!important] Your original notes remain yours
> Molecule stores descriptions, connections, reviews, and indexes in plugin data. Normal indexing, analysis, discovery, and review **do not edit your existing Markdown notes**. Creating a comparison note or an export is an explicit action that creates a **new file**.

You do not need to classify every note manually *(although you may if you choose to)*. Molecule is intended to do as much routine work as possible while allowing you to correct its understanding when useful.

---

## 2. The Molecule panel, top to bottom

Open the panel with the **Open Molecule** ribbon icon or the command **Molecule: Open Molecule sidebar**. The panel normally follows the active note. The note shown in the panel is the **focus note**—the note Molecule is currently describing or matching against others.

### Panel header and note status

- **Pin note / Unpin:** Keep the panel focused on one note while you navigate elsewhere, or return to following the active note.
- **Background status:** Shows whether background AI work is idle, processing, applied (finished), or needs attention. Click it for job details.
- **Local index:** Indicates whether the note has been indexed locally. Indexing is free and does not mean AI analysis has been performed. (Indexing is the process of telling Molecule which notes it should be working with.)
- **Description / AI analysis status:** Distinguishes saved/reviewed description information from whether AI analysis has been run.
- **Index this note / Repair local index for this note (free):** Appears when needed. Rebuilds local indexing information, not the note's Markdown.

If a note is excluded or outside the configured scope, Molecule explains that status. **Individual note eligibility** can override filename/tag eligibility for a particular note, but cannot extend the configured indexing folder.

### Description

This is **Layer A**: Molecule's structured representation of the focus note.

#### Core idea / key information

The central intellectual content of the note. For an argumentative note, this is usually its principal proposition. For a factual or reference note, it may be the key information rather than an argument.

A **core idea** is more specific than a topic. For example:

- **Topic:** Rest
- **Core idea:** Rest is a positive responsibility rather than merely the absence of productive work.

If an AI description exists, it may appear as an **AI suggestion / not accepted** until you explicitly save or approve it.

#### Other Major Ideas

An expandable list for **additional substantive propositions** that matter to the note but are not captured by its central idea. Use **+ Add another idea** only when genuinely useful.

This is not a checklist to fill for every note. Molecule should still be able to find relationships involving implications that you have not painstakingly listed.

#### Topics

What the note is **about**: subject labels such as `rest`, `parenting`, or `biblical interpretation`.

Enter multiple topics separated by semicolons (`;`). (If you prefer, you can change the settings so topics are separated by commas instead.)

#### Themes & Concepts

Broader recurring ideas, concerns, or conceptual threads running through the note. These may cross topic boundaries—for example, `stewardship`, `authority`, `responsibility`, or `dependence`.

Enter multiple items separated by semicolons.

**Topics** and **Themes & Concepts** are separate categories in the Intellectual Index. Neither is a substitute for the actual core idea.

#### Authorship

Indicates the relationship of the content to its author or compiler:

- **Original:** Primarily your own thinking or writing.
- **Mixed:** A combination of your own thinking and outside material.
- **Supplementary:** Primarily collected/reference material from other sources.
- **Uncertain:** Authorship cannot be confidently determined.

This distinction helps interpret a note appropriately. It does not change its source Markdown.

#### Saved AI analysis details

When available, this expandable area shows information about the AI analysis, such as the model and supporting excerpts. It is useful for understanding where a suggestion came from; you do not ordinarily need to open it.

#### Your notes and corrections

A place to record corrections, qualifications, or contextual notes about Molecule's interpretation. These are **Molecule metadata**, not edits to the note itself.

#### Saving and accepting

Each field has its own **Save** control and status, such as **Saved**, **Edited**, or **AI suggestion / not accepted**.

Two buttons below the fields offer different levels of commitment:

| Button | What it does |
|---|---|
| **Save Manual Changes** | Saves edited text fields without declaring the whole description reviewed. |
| **Accept & Save All** | Saves the populated description and marks it as reviewed/accepted. |

You can therefore correct one field without having to approve everything. A saved change to semantic text may trigger a **local, free embedding refresh**, so future discovery uses the updated representation.

**Browse Layer A review queue** opens the review tools explained in [[#7. The Layer A review tools]].

*Optional Principles and Scripture References may appear here when enabled; see sections 9 and 10.*

### Tools & AI Workflows

These buttons start work for the current focus note (or open a dialog in which you can confirm scope and processing choices).

- **Describe notes:** Run Layer A description analysis.
- **Discover connections:** Run Layer B connection discovery.
- **Describe + connect:** Perform the two stages together.
- **First-time semantic coverage (local / free)**
  1. Choose the indexing scope and optional excluded folders in Settings.
  2. Run **Index selected scope** in the Obsidian command palette to register eligible notes.
  3. In Molecule’s **Tools & AI Workflows** section, click **Build semantic coverage (free)**.
  4. Click **Build next 500 missing vectors** and repeat until coverage is complete.
    *(Registration -- indexing -- and semantic coverage are separate. Both are local, free operations. You may enter and save manual Layer A descriptions without generating vectors or calling an AI API.)* 
- **Check description quality (free):** Locally flag certain potentially weak AI Core Idea descriptions for human review. It is a triage aid, not an AI rewrite or a definitive quality judgment. (This feature identifies notes that)
- **Browse connection candidates (free):** Inspect locally ranked potential connections without sending them to the paid AI evaluator. Covered in [[#5. Working offline or without paid AI]].

> [!tip] Which button should I choose?
> For a new note, **Describe + connect** is the simplest route if you are happy to let Molecule proceed through both stages. Choose **Describe notes** first if you want to inspect or edit the description before discovery. Choose **Discover connections** when the note already has a usable representation.

AI analysis and relationship qualification require a configured OpenAI API key and can incur charges. Local indexing, local embeddings, and candidate browsing do not.

### Connections

This is the visible result of **Layer B**, not a list of every vaguely similar note.

Connections are grouped by **relationship type**. Only nonempty types appear. The main Connections section, each type group, and individual connection details can be expanded or collapsed independently.

**Collapse all / Expand all** controls the *relationship-type groups*, not every individual connection card.

#### Understanding the relationship labels

| Label                         | Meaning                                                                              |
| ----------------------------- | ------------------------------------------------------------------------------------ |
| **Equivalent**                | One note makes substantially the *same* argument as the other.                       |
| **Supports**                  | One note gives reasons or evidence strengthening the other's claim.                  |
| **Extends**                   | One note develops an idea further or carries it into new territory.                  |
| **Complements**               | The notes contribute different, compatible pieces to a fuller understanding.         |
| **Qualifies**                 | One adds a necessary limit, condition, or nuance to the other.                       |
| **Illustrates**               | One supplies a concrete example of an idea expressed in the other.                   |
| **Applies**                   | One puts an idea into practice or shows its implications in a situation.             |
| **Contrasts**                 | The notes differ in an illuminating way without necessarily disagreeing.             |
| **Challenges or Contradicts** | One calls the other's claim into question or directly opposes it.                    |
| **Related**                   | A meaningful relationship exists but is not well described by a more specific label. |
#### Individual connections

A collapsed connection shows a **clickable note title** and its saved Core Idea or a fallback excerpt. Expand it to see:

- **AI rationale:** Why Molecule thinks the ideas are meaningfully related.
- **Relationship type:** A dropdown to correct the classification without having to reject the relationship itself.
- **Review status:** **Not rated**, **Accepted**, or **Rejected**.
- **Accept / Reject:** Explicit decisions about the relationship.

**Not rated** means you have not personally accepted or rejected the connection. It does **not** mean the connection is unrelated or that the AI failed to select it. Automatic discovery may display recommended connections immediately without marking them personally accepted.

**Rejected connections** remain in a separate, normally collapsed group. They are retained rather than erased, and you can restore one.

#### Add connection manually

Creates a connection between the focus note and another note, with your chosen relationship type and explanation. No paid API call is needed.

#### Create comparison note

Opens a selection dialog for the focus note's discovered connections. Select **All connections**, **None**, or individual entries, then generate a **new Markdown note** with the focus note and selected connections embedded under relationship headings.

This is an explicit output operation; it does not insert links into or rewrite your existing notes.

*When enabled, Shared Scripture References appears after these controls, inside Connections. It is separate from Layer B and explained in section 10.*

### Related notes (existing links) / Local links

This separate section shows relationships already expressed by **ordinary Obsidian links** in your vault. The arrows indicate whether the focus note links *out* to another note or another note links *in* to it.

- **Refresh existing links** updates Molecule's local view of these links.
- These are **not AI-discovered connections**. They largely duplicate Obsidian's own linking information for convenient side-by-side reference.

*(You can turn this display off in settings if you prefer. It doesn't offer anything Obsidian's existing backlink panel doesn't already. But some users may appreciate having both types of links show up inside the same panel.)*
### Other note controls

**Individual note eligibility** is available here for ordinary notes. Use it to override a note's exclusion status without editing its Markdown or changing the scope of the entire vault.

---

## 3. Settings, top to bottom

Open **Obsidian Settings → Community plugins → Molecule → Settings**. The order below follows the v0.5.232 Settings screen.

### Indexing scope

**Indexing scope:** Choose **Selected folder and subfolders** or **Entire vault**. This determines which notes Molecule's local indexing is intended to cover.

**Indexed folder:** If folder scope is selected, choose the folder.

### Exclusion rules/Excluding notes and folders

Use **Excluded folders → Add excluded folder** to choose entire folders, including subfolders. For special filename rules, expand **Advanced filename exclusion rules (regex)**. The examples and tutorial link explain how filename patterns work. 

Rules use **regular expressions** matched against filenames without `.md`. Enable/disable individual rules, add rules, or remove them.

**Preview scope and exclusions** reports how many notes are in scope, excluded, and eligible. Use this before processing a large vault.

### Index

**Index selected scope → Run indexing:** Build or refresh the local note index without AI charges. This adds/refreshes notes in scope; it does not automatically purge previously indexed notes from other locations.

### Scripture catalog controls — optional

**Enable Scripture reference catalog**, **show empty books**, and **show empty chapters** are covered in [[#10. Optional feature — Scripture Reference Catalog]]. They are unrelated to the normal Layer A/Layer B setup.

### Connection candidate search boundary

This determines **where Molecule looks for possible partner notes**, independently of where the focus note lives.

**Search candidate notes in:**
- **Indexing scope (recommended):** Search the configured index area.
- **A separate folder and its subfolders:** Use a different candidate pool.
- **Entire vault:** Explicitly allow the widest search.

**Use Obsidian tags as matching evidence:** Optionally use real Obsidian tags as retrieval clues; this does not rewrite saved topics or themes.

**Per-note exceptions:** View note-specific eligibility overrides. Set an override from the main Molecule panel.

**Exclude candidates with tags:** Enter tags whose notes should be excluded as candidates (for example, archival or reference-only tags). These exclusions do not prevent you from directly opening a note as the focus note.

**Include nested tags in candidate exclusions:** If enabled, excluding `#archive` also excludes `#archive/old`.

**Layer B connection review:**
- **Automatic (recommended):** AI-selected relationships appear in Connections without requiring an extra acceptance step.
- **Review before accepting:** Hold new relationships for review. Existing decisions are preserved.

Automatic display does **not** mean you personally rated the connection as Accepted.

**Show development tools** and **Diagnostic watchlist:** Optional diagnostics; see section 11.

**Candidate folder:** Appears if you selected a separate candidate-search folder.

**Preview candidate search boundary:** Counts eligible candidates after scope, filename, and tag exclusions, without reading note bodies or calling AI.

### Authorship

**Authorship mode:** Treat all notes as yours, treat all as mixed, or **Detect using rules**.

When detection is enabled, configure the **Frontmatter property** and **Value identifying original work**. 

You can also correct authorship for individual notes in the Description section.

### Comparison notes

**New note destination:** Choose the vault root, the current note's folder, or a designated folder.

**Designated folder:** Choose or type its path when that destination mode is selected.

These settings apply to newly generated comparison notes, including optional Scripture-based versions, and to core idea exports.

### Analysis workflow

**Require reviewed descriptions for future relationship discovery:** When enabled, Layer B uses only manually approved Layer A descriptions. Use this if you want a human review checkpoint; leave it off for a more automated workflow.

**Relationship discovery:** Enable or disable on-demand AI relationship discovery.

**Additional frontmatter properties for candidate discovery:** Optional property names whose values can help retrieval. These are *clues*, not automatically saved Topics or Themes & Concepts.

**Prioritize discovery properties in listed order:** Optionally weight earlier listed properties somewhat more heavily.

**Adaptive semantic qualification:** Controls the local candidate-qualification behavior.

**Explore below the qualification threshold:** Reserves some evaluation attention for lower-ranked candidates to check whether the local threshold missed something worthwhile.

**Cap connection candidates / Connection candidates per note:** If a cap is enabled, it limits how many qualified, unevaluated candidates can be sent for a note. Disabling the cap permits all eligible qualified candidates, subject to other exclusions and processing constraints. Larger evaluations may cost more.

> [!warning] Candidate settings affect discovery quality
> More candidates do not automatically mean better connections. Overly restrictive boundaries, exclusions, or thresholds can hide valuable relationships. Adjust one major variable at a time if testing.

### Analysis display

**Prefill Core Idea with text preview:** When no saved description exists, show a local editable excerpt. This is a convenience preview, **not** an accepted AI interpretation.

**Show existing local links:** Controls the separate Related Notes / Local Links section.

**Show ideas behind principle matches:** Optional principle detail; see section 9.

### Principle registry — optional

**Enable principle matching** and its registry configuration are explained in section 9. You can skip the entire group for ordinary use.

### AI analysis

**OpenAI API key:** Your own API credential for paid analysis/discovery. It is stored in Obsidian plugin settings **without encryption**; do not share your plugin data or screenshots containing it.

**Model:** Choose the available OpenAI model for analysis.

**OpenAI API account:** Links to API keys, usage, and billing pages. Molecule cannot read your billing account for you.

**Analyze selected notes → Choose notes…:** Start an analysis workflow for a chosen set of notes rather than only the active note.

### Pilot interpretations — specialized

**Import bundled Technology pilot:** Imports a historical set of 18 sample interpretation records where matching notes exist. This is a specialized development/demo aid, **not part of the normal workflow**.

### Export data

**Export Molecule data → Create export file:** Creates a new JSON export of Molecule's metadata and index. The API key is omitted. The export is a **new vault file**, not a rewrite of your notes.


---

## 4. A normal start-to-finish workflow

The simplest practical workflow is:

### Step 1 — Configure scope and AI

In Settings, choose the indexing scope, review exclusions, and select the candidate-search boundary. Enter your API key and choose a model if you intend to use paid AI.

Set the comparison-note destination now if you expect to generate outputs.

### Step 2 — Build the local index

Use **Index selected scope → Run indexing**. This is free and leaves note Markdown unchanged. *(Find this in the settings, where you've configured the discovery folders.)*

For a large vault, index first and use the estimator (section 6) before committing to a large AI run.

### Step 3 — Open a focus note

Open a note in Obsidian and the Molecule sidebar. Check that the note is eligible and indexed.

### Step 4 — Describe the note

Choose **Describe notes** (or **Describe + connect** for a streamlined run). Molecule proposes a Core Idea, Topics, Themes & Concepts, and other description information.

You can leave AI suggestions as suggestions, save individual corrections, or use **Accept & Save All** to mark the description reviewed. Review is not mandatory unless your settings require it for discovery.

### Step 5 — Prepare local semantic coverage

Molecule uses local semantic **embeddings**—numerical representations of text—to find candidate notes. Saved Layer A descriptions are preferred; eligible notes without descriptions can use shorter **fallback representations**.

For a large or incompletely covered vault, run **Molecule: Semantic coverage — build local fallback embeddings (free)** from the Command Palette as needed. This processes missing "vectors" locally in batches. A note can be indexed without yet having a usable embedding.

> [!note] Indexing is not the same as semantic coverage
> **Indexing** records local note information. **Embedding coverage** prepares notes for semantic similarity search. **AI description** and **AI connection evaluation** are additional stages. They are not interchangeable.

### Step 6 — Discover connections

Choose **Discover connections** for the focus note. Molecule searches locally for candidates, then sends qualifying pairs to the configured AI model for **independent relationship judgments**.

Depending on the workflow dialog and processing mode, work may run immediately or as a background job. Check the background indicator/status when applicable.

A candidate rejected by the AI does not become a displayed connection merely because it had a high similarity score.

### Step 7 — Inspect the results

Open **Connections**. Browse relationship groups and note previews. Expand interesting connections to read the rationale.

Use **Accept** or **Reject** where you want an explicit decision. Change **Relationship type** separately if the relationship is valuable but the category is wrong.

You do not need to rate every result during normal use.

### Step 8 — Generate a comparison note (optional)

Click **Create comparison note**, choose which connections to include, and create a new Markdown note. Read the embedded notes together to explore the resulting intellectual structure.

You can stop at the Connections panel if you do not need a separate note.

### Step 9 — Continue incrementally

Repeat for other focus notes or use **Analyze selected notes** for batches. Molecule retains saved descriptions, embeddings, evaluation results, and explicit decisions so that ordinary use need not begin from scratch each time.

---

## 5. Working offline or without paid AI

You can use meaningful parts of Molecule without an API key or without making a new paid call.

### A. Enter Description information manually

Open the focus note and type directly into **Core idea / key information**, **Topics**, **Themes & Concepts**, **Authorship**, and **Your notes and corrections**. Add **Other Major Ideas** if warranted.

Use individual **Save** controls or **Save Manual Changes**. You can mark the full description reviewed with **Accept & Save All**.

This information is stored in Molecule metadata, not the Markdown note. It can improve the note's local semantic representation and future discovery. **Manual entry does not automatically run paid Layer B evaluation.**

### B. Browse connection candidates (free)

Click **Browse connection candidates (free)** in the panel, or run **Molecule: Browse connection candidates (free, current note)**.

This uses local embeddings to rank potential matches. It is an **exploration tool**, not a list of AI-verified intellectual relationships.

The browser offers filters such as:

- **Qualified**, **Below threshold**, **All ranked**, **Next API request**, **Manually excluded**, and **Evaluated**.
- **Representation:** Both types, Layer A only, or Fallback only.
- **Copy candidate report:** Export a chosen rank range for inspection.

For an individual candidate you can **Open note**, manually **Accept** or **Reject** the relationship, **Exclude from API**, or **Protect** it. There are also source-specific bulk actions below a chosen similarity score.

**Protect** is a candidate-control decision, not proof that a relationship is substantive. **Exclude from API** prevents future paid evaluation of that candidate for this focus note; it is not the same as rejecting the intellectual relationship. Bulk actions should be used carefully.

A manual acceptance asks you to assign a relationship type. This lets you create a useful connection without waiting for an AI judgment.

### C. Add a connection manually

Use **Add connection manually** in Connections. Choose another note, select the relationship type, and supply a short explanation.

This is particularly useful for a meaningful relationship you already know exists but that automated discovery did not find.

### What “offline” does and does not mean

Local indexing, local embeddings, candidate browsing, and manual annotations do not require paid AI requests. Some first-time local-model setup may require downloading model assets if they were not bundled with the installation. A fully bundled runtime can avoid that initial download.

The **AI description** and **AI qualification** stages still require an API connection. Local similarity scores alone cannot establish the substantive relationship Molecule is designed to discover.

---

## 6. The full-vault cost estimator

Open the Command Palette and run:

**Molecule: Estimate full-vault processing cost (local / free)**

This is a **read-only planning tool**. It does not start analysis, make paid requests, clear caches, or edit notes.

It estimates:

- The cost of processing the eligible vault **from scratch** under the current assumptions.
- The **remaining** modeled work after accounting for existing descriptions and reusable results.
- Layer A descriptions, optional principle matching, and Layer B evaluation, separately and in combination.
- Immediate versus background-processing scenarios where supported.

The estimator is also useful as a **progress census**: it can help show how much of the configured work has already been completed.

> [!warning] Estimates are not invoices
> Layer B candidate volume for an unprocessed vault is partly projected, not known exactly. Model prices in this version include **hardcoded assumptions** that may become stale. The report does not measure historical money spent. Check current API pricing separately before making a substantial budget decision.

For an unfamiliar vault, run the estimator **before** a large AI batch and revisit it after some work has been completed.

---

## 7. The Layer A review tools

Molecule provides two complementary ways to review descriptions.

### Browse Layer A review queue

Open from the Description section or the Command Palette command **Molecule: Browse Layer A review queue**.

This browser helps locate notes whose descriptions need attention. Open a listed note in the editor, inspect its Molecule Description, correct individual fields if needed, and save or accept them.

Because review states are stored separately, you can distinguish saved/approved content from AI suggestions that have not been explicitly accepted.

### Check description quality (free)

Use **Check description quality (free)** in Tools & AI Workflows, or the corresponding Command Palette command.

This runs a **local heuristic check** for certain conspicuous problems in AI-generated Core Ideas—for example, descriptions that are little more than placeholders or references, or source notes whose content may not have been adequately interpreted.

It does **not** re-analyze notes using AI and does not definitively establish that a description is wrong. It is intended to **prioritize human attention**, not impose an exhaustive manual-review requirement.

The persistent review sidebar lets you open flagged notes while retaining access to the normal Molecule panel. After correcting or approving a description, refresh the review list to update its status.

---

## 8. The Intellectual Index

Open with **Molecule: Browse intellectual index (topics and themes, free)**.

The Intellectual Index is a dockable browser of the conceptual labels Molecule has collected. Its two main categories are:

### Topics

Browse notes by **what they are about**.

### Themes & Concepts

Browse notes by **recurring conceptual threads** that may cut across subjects.

The browser supports searching, counts, navigating to notes, and managing labels. It is useful both for finding notes and for improving consistency in the vocabulary of your intellectual index.

### Renaming, merging, and corrections

- **Rename:** Change the display name of a topic or theme/concept while retaining its stable identity.
- **Merge:** Combine duplicate or synonymous entries in the *same category*.
- **Correction rules:** Manage mappings that normalize future labels. A correction rule is distinct from merging existing indexed identities.
- **Near-duplicate audit:** Locally identify labels that may be duplicative; review before merging.
- **Capitalization preferences:** Control presentation consistency.

These operations manage Molecule's index metadata; they do not rewrite your original notes.

### Linking to an index entry from a note

Index entries have **stable, category-specific IDs** and support copyable `molecule-index:` links. You can manually place a generated link in a note if you want a direct path back to that topic or concept in Molecule.

Molecule does **not** automatically insert these links into existing Markdown. Links created through its supported mechanism work in Obsidian's Reading View and Live Preview.

When indexed labels are merged, redirects preserve supported references to older IDs. The read-only link scanner is designed for generated inline links and may not recognize every possible Markdown link syntax.

*The third, optional Scripture tab is explained separately in section 10.*

---

## 9. Optional feature — Principles

### What is a principle?

A **principle** is a generalizable proposition that can apply across multiple situations or notes.

Compare:

- **Topic:** Parenting
- **Theme:** Responsibility
- **Core idea:** Children learn responsibility more effectively when entrusted with meaningful work.
- **Principle:** Responsibility is developed through the exercise of real responsibility.

Principles are not merely extra topic labels. They are intended to identify **transferable ideas** that can be illustrated or applied in multiple domains.

### Setting up a principle registry

In Settings, enable **Principle matching** and configure the **Principle registry**.

A registry is a folder of existing Markdown notes, each representing a principle. Each valid principle needs:

1. A stable, unique **Principle ID** in the configured frontmatter property.
2. A **name**, sourced from a property, filename, or first heading.
3. A **definition**, sourced from a property, heading, or first nonempty paragraph.

Use **Preview registry** to find missing or duplicate fields. Invalid entries are skipped; Molecule does not invent IDs or repair your notes.

### How matching works

When enabled, eligible Layer A AI processing can propose principles from the registry that apply to a note. The Description panel gains a **Principles** area with:

- **Confirmed principles**
- **Suggestions awaiting review**
- **Rejected suggestions**
- **Add principle manually**
- Optionally, **Ideas used to identify principle matches** and **Possible new principles (not in registry)**

You can confirm, reject, or add associations without editing the underlying principle notes.

Principle matching is **optional** and is not required for normal semantic connection discovery. In this version, automated principle submission is limited by note eligibility/type (notably notes classified as `idea`); a note without principle suggestions is not necessarily an error.

Principle matching may involve AI cost when run as part of Layer A processing. The registry validation and local UI operations do not.

---

## 10. Optional feature — Scripture Reference Catalog

The feature is called the **Scripture Reference Catalog** in Settings. In the panel it appears as **Scripture References** and **Shared Scripture References**; in the Intellectual Index it appears as the **Scripture** tab.

### Why it is separate from Molecule's core

This feature indexes **explicit associations between notes and Bible passages**. It does **not** evaluate the ideas in those notes and does **not** feed references into Layer A descriptions, semantic candidate selection, or Layer B relationship judgments.

Two notes citing the same passage may have very different arguments. Shared references are useful navigational information, **not evidence that the notes have a meaningful semantic connection**.

The feature is therefore **functionally independent**, but integrated into the interface where a reader would naturally look for related material.

It works locally and does not require an API key.

### Enabling it

In Settings, turn on **Enable Scripture reference catalog (experimental)**. Despite the historical setting label, this functionality is included in the accepted v0.5.232 build.

You can also choose whether the Scripture browser displays **empty books** (on by default) and **empty chapters** (off by default).

The initial browser covers the **66 books of the Protestant canon**, using traditional verse numbering, including passages sometimes omitted or bracketed in modern editions. Molecule does not make textual-critical judgments.

### Scripture References in the Description panel

Below the Description fields and their save/accept controls, the optional **Scripture References** section shows passages associated with the focus note.

You can:

- **Add** references manually.
- **Remove** an association.
- Expand the list to see more than the initial few entries.
- Open **Manage references…** and use **Preview references in this note (local / free)**.

The preview scans **only the current note**, proposes recognizable citations, and lets you add them individually. It does not automatically index all detected citations or scan the vault.

It understands many ordinary full and abbreviated book names, chapter-only citations, chapter ranges, verse ranges, cross-chapter ranges, and references divided by commas or semicolons. It can also detect references whose visible text is inside an aliased Obsidian wikilink while verse numbers follow the link.

For ambiguous abbreviations such as `Ez`, Molecule avoids guessing. For `f`/`ff` (following verse[s]), it can offer the **starting verse only**, without inventing an endpoint.

### The Scripture tab in the Intellectual Index

Browse by **book → chapter → verse**. The left navigation and matching-note results scroll independently.

Associations retain their actual scope:

- **Whole book**, such as Romans.
- **Whole chapter or chapter range**, such as Matthew 5–7.
- **Explicit verse or verse range**, such as John 3:16–18 or John 3:16–4:3.

The results show each matching note once and display **only the passages relevant to the selected book, chapter, or verse**. Cross-chapter references respect actual chapter boundaries.

A whole-chapter association is not silently expanded into every verse of that chapter.

### Shared Scripture References in Connections

When two notes have overlapping indexed passages **at compatible levels of specificity**, Molecule can display them under **Shared Scripture References** inside Connections, below the normal Layer B action buttons.

Examples:

| Focus note | Other note | Shared reference? |
|---|---|---|
| John 1 | John 1 | Yes — same whole chapter |
| John 1 | John 1:12 | No — different scopes |
| Matthew 5–7 | Matthew 6 | Yes — overlapping chapters |
| Matthew 5–7 | Matthew 6:9 | No — different scopes |
| John 3:16–4:3 | John 4:2 | Yes — overlapping verses |
| Romans (whole book) | Romans (whole book) | Yes |
| Romans (whole book) | Romans 8 | No — different scopes |

Each result shows **both passages**, so you can see the nature and extent of the overlap.

This subsection is visually inside Connections but is **not a Layer B AI result**. The separate Related Notes / Local Links section still shows ordinary Obsidian links.

### Three comparison-note choices

The original **Create comparison note** button produces a note from Layer B connections only.

When Scripture is enabled and shared references exist, two additional buttons appear beneath the shared-reference list, **even when that list is collapsed**:

- **Create Scripture comparison note:** A new note containing selected Scripture-linked notes and the passages shared from both sides.
- **Create combined comparison note:** A new note containing the usual Layer B comparison structure **plus a separate Shared Scripture References section at the end**.

You select which notes/connections to include. If a note has both a semantic connection and a shared Scripture association, the combined output may include it in both sections because those are **different kinds of relationship**.

All three options create **new notes only**. None modifies the source notes.

### What this feature does not do

- It does not automatically index every Bible reference in your vault.
- It does not guarantee recognition of every citation style or implied passage.
- It does not assume that a whole-chapter note and every verse-specific note in that chapter are intellectually related.
- It does not change Layer A, Layer B, or the AI evaluation prompt.
- It does not require an internet connection or paid AI calls during use.

---

## 11. Optional feature — Diagnostics and development tools

Molecule has a range of free, local tools for inspecting behavior, investigating missed connections, and testing changes. **You do not need them for everyday use.**

Enable **Show development tools** in Settings to reveal additional developer-oriented commands. Some generally useful local commands are available without that toggle.

### Commonly useful tools

| Tool | When to use it |
|---|---|
| **Background processing status (free)** | Check ongoing, completed, interrupted, or failed background jobs. |
| **Repair semantic embedding for current note (local / free)** | A note's saved representation changed or its vector is missing/stale. |
| **Semantic coverage — build local fallback embeddings (free)** | Prepare semantic coverage for eligible notes without Layer A. |
| **Browse connection candidates (free)** | Investigate plausible local matches without paid evaluation. |
| **Connection trace (read-only, current note)** | Investigate why a particular connection was or was not found. |
| **Threshold Calibration Lab (free, current note)** | Examine the effect of candidate thresholds. |
| **Diagnose Layer B rename references (read-only / free)** | Check path/reference integrity after note renames. |
| **Scan vault Molecule index links (local / free)** | Inspect supported index-link references in the vault. |
| **Copy last discovery batch diagnostic (free)** | Retrieve details from the latest Layer B batch for troubleshooting. |

### Development-only inspections

When enabled, additional tools may include **Inspect semantic cache**, **Layer B semantic API preflight**, **Layer B evaluation ledger status**, **Layer B corpus inventory**, and **Layer B evaluation details**.

These help distinguish:

1. A note that was **outside the candidate search boundary** or excluded.
2. A note without a valid **embedding**.
3. A candidate that ranked **below the local threshold**.
4. A candidate that reached the AI but was **not selected**.
5. A connection that exists but was **rejected by the user**.
6. A relationship that was found but given the **wrong type**.

These are different problems; changing the similarity threshold will not repair a connection that the AI explicitly rejected.

### Important cautions

- Read-only diagnostics do not modify source Markdown or make paid calls.
- **Repair** commands may update Molecule-owned caches.
- **Reset Layer B** developer controls can clear stored connections for the focus note. They are not read-only; do not use them casually.
- Candidate exclusions, manual rejections, and bulk actions can affect later discovery. They are decisions, not mere diagnostics.
- Keep failed tests, rejected pairs, and false positives when evaluating quality. More connections alone do not prove better discovery.

---

## 12. Optional feature — Exporting Core Ideas

Molecule's **Export Core Ideas** feature lets you create a single Markdown inventory of the ideas contained in a selected group of notes. This is useful when you want to review, compare, organize, or rearrange ideas without opening each note individually.

For example, you might use it to survey your notes on a particular subject, identify material for a book or article, develop an outline, or share a collection of ideas with an AI assistant for further analysis.

The export uses Core Ideas already saved in Molecule's Layer A analysis. It does not analyze notes again, make API calls, or change your original notes.

### How to Export Core Ideas

1. Open Obsidian's **Command Palette** (`Ctrl+P`, or `Cmd+P` on macOS).
2. Search for and select **Molecule: Export core ideas**.
3. Choose which notes to include:
   - **Folder only:** Includes Markdown notes directly inside the selected folder, excluding its subfolders.
   - **Folder and subfolders:** Includes Markdown notes in the selected folder and all its nested subfolders.
   - **Filename range (all folders):** Includes notes whose filenames fall within the specified range, regardless of which folder contains them. Both endpoints are inclusive.
4. If using a folder-based selection, click **Choose folder** and select the folder.
5. If using a filename range, enter the starting and ending filenames without the `.md` extension.
6. Optionally enable **Include Other Major Ideas**. This is turned off by default.
7. Click **Create export note**.

Molecule creates a new Markdown note containing the inventory and opens it in Obsidian.

### What's Included in the Export?

Each inventory contains:

- **A summary header** showing the selection scope, total number of notes, number with Core Ideas, and number missing Core Ideas.
- **A linked filename** for each included note, using Obsidian's internal `[[wikilink]]` format.
- **The saved Core Idea** for each note, displayed beneath its filename.
- **Other Major Ideas**, if the option was enabled and those ideas have been saved.
- **MISSING CORE IDEA**, displayed prominently for any note without a saved Core Idea.

Entries are sorted by filename, using natural numeric ordering where possible.

Each entry is a separate Markdown block, making it easy to move, group, or reorganize entries while developing an outline.

### Where Is the Export Saved?

The new inventory is saved according to Molecule's existing **Create comparison/connection note** destination setting.

The export dialog displays the destination before you create the note.

The inventory is a separate Markdown file. Editing, rearranging, or deleting its contents does not change the original notes or their saved Layer A analyses.

### Important Notes

**Existing descriptions only.** The exporter uses saved Layer A Core Ideas, including AI-generated descriptions that have been saved but not necessarily reviewed or edited. For the most useful results, review and refine your Core Ideas before creating a working inventory.

**Missing Core Ideas.** If a note does not have a saved Core Idea, Molecule displays **MISSING CORE IDEA** rather than substituting a preview or excerpt of the note. This helps distinguish notes that need attention.

**Other Major Ideas are optional.** The checkbox is off by default to keep inventories concise. When enabled, Molecule includes additional major ideas that have been saved for the notes.

**Filename ranges search across folders.** A filename range is not limited to the currently open folder. For example, a range from `7814-001` through `7814-100-99` searches matching filenames across all

## 13. Safety, costs, and common questions

### Does Molecule edit my notes?

**Not during ordinary use.** Descriptions, connections, indexes, and review states live in plugin data. Explicit **comparison-note creation** and **data export** create new files. Molecule does not automatically insert links, rewrite frontmatter, or reorganize your notes.

### Does every note need an AI description?

**No.** Local fallback representations let eligible notes participate in semantic retrieval without a complete Layer A description. A saved, accurate Core Idea generally provides a more intentional representation, but exhaustive manual classification is not required.

### Does a high semantic similarity score mean a meaningful connection?

**No.** Similarity determines which candidates are worth examining. The paid qualification stage asks whether the actual ideas have a substantive relationship.

### Can I use Molecule without an API key?

**Yes, partially.** Local indexing, manual descriptions, local semantic embeddings, candidate browsing, manual connections, the Intellectual Index, and the optional Scripture catalog do not require paid AI evaluation.

### Is background processing required?

**No.** Immediate and background modes serve different workload sizes and circumstances. Background processing is especially useful for larger batches, but its status should be monitored.

### What should I back up?

Back up the vault and the **entire Molecule plugin folder**, including `data.json` and runtime-generated caches, ledgers, and job records, before replacing plugin files. Those files are **not** included in a clean new-user distribution package because they are specific to your vault.

### Is v0.5.232 a published Community Plugin?

No. It is the accepted canonical project build, packaged for manual installation. A public release would require further clean-install verification and third-party/model redistribution license checks.

---

## Glossary

| Term                            | Meaning                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Focus note**                  | The note currently being described or matched against candidate notes.                                                                                                                                                                                                                                                                                   |
| **Layer A**                     | The structured description of a note's intellectual content.                                                                                                                                                                                                                                                                                             |
| **Core Idea**                   | The note's main proposition or key information.                                                                                                                                                                                                                                                                                                          |
| **Other Major Ideas**           | Additional substantive propositions in the same note.                                                                                                                                                                                                                                                                                                    |
| **Topic**                       | What a note is about.                                                                                                                                                                                                                                                                                                                                    |
| **Theme / Concept**             | A recurring idea or conceptual thread, potentially across topics.                                                                                                                                                                                                                                                                                        |
| **Principle**                   | A generalizable proposition represented in an optional registry.                                                                                                                                                                                                                                                                                         |
| **Layer B**                     | Semantic candidate discovery followed by AI relationship qualification and classification.                                                                                                                                                                                                                                                               |
| **Candidate**                   | A note retrieved as a possible match, before a substantive relationship has been established.                                                                                                                                                                                                                                                            |
| **Embedding**                   | A locally generated numerical representation used to compare semantic similarity.                                                                                                                                                                                                                                                                        |
| **Fallback representation**     | A shorter local text representation for an eligible note without saved Layer A content.                                                                                                                                                                                                                                                                  |
| **Qualification**               | Deciding whether two notes have a meaningful relationship at all.                                                                                                                                                                                                                                                                                        |
| **Classification**              | Assigning the type of a relationship after recognizing that it exists.                                                                                                                                                                                                                                                                                   |
| **Not rated**                   | A displayed relationship without an explicit human Accept/Reject decision.                                                                                                                                                                                                                                                                               |
| **Evaluation ledger**           | Stored results of prior AI pair evaluations, including non-selected pairs.                                                                                                                                                                                                                                                                               |
| **Comparison note**             | A newly generated Markdown note embedding selected related notes.                                                                                                                                                                                                                                                                                        |
| **Intellectual Index**          | Browsable Topics and Themes & Concepts metadata, with optional Scripture tab.                                                                                                                                                                                                                                                                            |
| **Scripture association**       | A locally indexed link between a note and an explicit Bible book, chapter, or passage.                                                                                                                                                                                                                                                                   |
| **Shared Scripture References** | Locally identified passage overlaps between notes; independent of Layer B.                                                                                                                                                                                                                                                                               |
| **Serendipitous connection**    | An unexpected but intellectually defensible relationship, not merely a superficial overlap.                                                                                                                                                                                                                                                              |
| **Vector**                      | A numerical, internal representation of a note's meaning, expressed as a list of numbers. <br><br>Molecule uses vectors (also called *embeddings*) to compare notes based on their semantic similarity rather than just matching words. Vectors help Molecule identify potential connections, which can then be evaluated for intellectual significance. |

---

*Guide for Molecule v0.5.241.*
