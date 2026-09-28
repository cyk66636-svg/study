---
name: link-numeric-citations
description: Use when a paper, presentation, or exported document has numbered citations whose formatting or navigation to the matching reference-list entries needs correction.
---

# Link Numeric Citations

Make each visible citation marker correctly formatted and link its numbers to their intended references. A superscript number alone is not a working link.

## Detect and map

1. Inspect the actual input, not just its filename: DOCX contains word/document.xml; PPTX contains ppt/presentation.xml; PDF starts with %PDF-; Markdown and HTML are text. If the extension disagrees with the contents, process the actual format and save the result with its correct extension without overwriting the original. If the user requests a new artifact, use its requested output format. For a legacy, scanned, or unrecognized file, identify a safe editable source or conversion path before editing.
2. Identify the required styles for **in-text markers and bibliography labels separately**, bibliography order, managed citation fields, and every in-text number. Map each number to exactly one source; repeated citations share the same target. Do not invent sources or guess an ambiguous match. Preserve brackets, punctuation, and the established numbering rules. For Chinese superscript style, set both the complete in-text marker and each bibliography entry's bracketed number label as true superscripts unless a school, journal, or template specifies otherwise. Check bibliography paragraph indentation independently.

## Position citations

When adding a new citation in Chinese prose, default to placing its marker after the paragraph's final relevant text and immediately before the closing `。`. Use a sentence- or clause-level position inside the paragraph only when that location is needed to show which specific claim the source supports, or when the requested style requires it; then place the marker before that claim's closing `。` or `；`. Do not append a marker after punctuation. When a task only formats or links existing citations, keep their positions; audit and report any markers that are not at the paragraph end instead of silently moving them.

## Apply by format

- **DOCX/Word:** Preserve Zotero, EndNote, or other managed fields and use that manager's update/link workflow. Otherwise bookmark each bibliography entry and insert a hyperlinked Word cross-reference of type **paragraph number**, not paragraph text. Use real list numbering and dynamic fields when renumbering is expected. For typed labels that cannot safely be converted, link the visible number to its entry bookmark and update displayed numbers after any reorder. When superscript is required, apply Word's actual superscript formatting to every run of each complete in-text marker, including linked number runs, and to each bibliography entry's bracketed number label when that label also requires superscript; keep the following reference text at the baseline. Check inherited paragraph styles: a `Normal` style with two-character first-line indentation can shift bibliography entries even when the labels have no leading spaces. If the required format says 顶格, set both first-line and left indentation to zero on the bibliography paragraphs, then check wrapped lines. Use the documents skill for DOCX authoring and visual verification.
- **PPTX/PowerPoint:** Treat each visible citation number, including numbers within a group, as independently clickable text or a shape. PowerPoint's ordinary internal link targets a **slide**, not an individual reference row. Link to a shared references slide only when page-level navigation meets the request; for exact per-reference navigation, use a dedicated appendix slide for each cited source. Preserve the slide's typography and layout, and assess the added slide count before changing a large deck. Use the presentations skill to edit and render the PPTX.
- **Markdown/HTML:** Give each reference a stable id and link each visible superscript number to that id, for example <sup>[<a href="#ref-smith-2024">1</a>]</sup> and <li id="ref-smith-2024"><sup>[1]</sup> Reference</li> when the bibliography labels also need superscripts.
- **PDF:** Prefer adding links in the editable source, then export and verify the PDF. For a PDF-only input, inspect whether text and link annotations can be edited reliably; use the PDF skill and do not claim a scanned image has working citation links.

A range such as [5–7] has no visible 6 to click. Follow the required style; expand to [5,6,7] with separate links only when every source must be directly clickable. If that conflicts with a required range style, ask which requirement takes priority.

## Verify

Check every number-to-source mapping, including repeated and grouped citations, after editing or renumbering. Verify in-text marker formatting, bibliography label formatting, bibliography paragraph indentation, and marker placement as separate checks against the required style. For new paragraph-level citations, confirm that each marker is immediately before the final `。`; for citations supporting a sentence or clause, confirm placement before that claim's punctuation. Test representative links in Word, PowerPoint Slide Show, or the final browser/PDF viewer as applicable. Confirm that any exported PDF retained the links and that typography and layout remain intact. Report a PPTX link to a shared references slide as slide-level navigation, never as a jump to a specific row.

This skill handles navigation and numbering. Use the paper-ai skill separately when the task also requires finding sources or checking whether a source supports a claim.
