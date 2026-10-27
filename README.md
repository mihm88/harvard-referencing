# Harvard Referencing

A Codex skill for auditing and correcting UEL Cite Them Right Harvard citations and reference lists while preserving the manuscript's academic content.

The skill is named `apply-harvard-referencing`. Its interface display name is **UEL Harvard Dissertation Auditor**.

## What it does

- Inventories in-text citations, quotations, figure and appendix citations, and reference entries.
- Cross-matches citations and references to flag missing entries, uncited entries, duplicates, and author-year conflicts.
- Checks author-date formatting, quotation locators, secondary referencing, and reference-list ordering.
- Provides source-format guidance for journal articles, books, chapters, conference papers, theses, reports, standards, datasets, and web pages.
- Reports missing metadata and uncertain cases instead of inventing details.

It is intended for dissertations, theses, essays, assignments, manuscripts, citation inventories, and Word documents.

## Referencing standard

Harvard has institutional variants. The skill uses this order of authority:

1. Current module, supervisor, or institutional instructions.
2. The Harvard guide explicitly designated for the task.
3. The bundled core UEL/Cite Them Right rules.
4. The bundled 12th-edition dissertation source-format digest, for relevant source types.
5. Clearly labelled assumptions for cases not covered above.

The bundled four-page UEL PDF is legacy guidance based on the 9th edition. It does not override current institutional requirements. The Markdown digests describe their basis in supplied extracts of the 12th edition; those extracts are not included as separate files in this repository.

## Repository structure

```text
apply-harvard-referencing/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── guide-rules.md
    ├── dissertation-source-formats-12th_Codex.md
    └── how-to-harvard-reference.pdf
```

- `SKILL.md`: audit workflow, safeguards, and expected outputs.
- `agents/openai.yaml`: interface name, description, and example prompt.
- `references/guide-rules.md`: core citation and reference-list rules.
- `references/dissertation-source-formats-12th_Codex.md`: dissertation-focused reference templates.
- `references/how-to-harvard-reference.pdf`: bundled UEL library guide.

## Usage

Load the `apply-harvard-referencing` folder using your Codex environment's skill-loading process. This repository contains skill instructions and reference material, not a standalone citation-processing application.

Once the skill is available, use a prompt such as:

```text
Use $apply-harvard-referencing to correct the Harvard citations and
reference list in my dissertation without changing its academic content.
```

Provide the manuscript and any current module or institutional referencing requirements. Identify the Harvard guide that should control the task. If you want missing source metadata retrieved or verified online, request that explicitly.

For Word documents, the workflow also calls for an available Word-document skill and a structure-preserving editing and rendering process.

## Expected outputs

For pasted text:

- Corrected text with citation and reference changes only.
- An itemised audit log.
- A compliance summary.

For Word documents:

- A clean corrected copy named `<original-stem>_Codex.docx`.
- A separate audit named `<original-stem>_Harvard_Audit_Codex.md`.

The workflow preserves the original file and calls for layout inspection and a check that non-citation content remains unchanged. It reports counts of checked items, corrections, unmatched items, duplicates, missing locators, incomplete metadata, unsupported cases, and assumptions.

## Safeguards and limitations

- Academic arguments, prose, quotations, findings, numbers, and document structure should remain unchanged unless broader editing is expressly authorised.
- Missing authors, dates, page numbers, titles, DOIs, and other metadata must not be invented.
- Uncited references are retained and flagged rather than automatically deleted.
- Citation-format compliance is not source verification, plagiarism assessment, CASP appraisal, or proof that a source supports a claim.
- Specialist source types outside the bundled templates require confirmation against the controlling guide.

## Licensing and third-party material

No repository-wide license has been added. This repository is not presented as MIT-licensed.

The bundled UEL PDF is third-party material and has no stated redistribution license in the supplied copy. Its inclusion does not grant permission to reuse or redistribute it. Check applicable rights and permissions before redistribution, and assess the rights to other reference material separately before applying any repository-wide license.
