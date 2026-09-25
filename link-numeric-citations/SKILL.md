---
name: link-numeric-citations
description: Use when a paper, presentation, or exported document has numbered citations whose formatting or navigation to the matching reference-list entries needs correction.
---

# Link Numeric Citations

Make each visible citation marker correctly formatted and link its numbers to their intended references. A superscript number alone is not a working link.

## Detect and map

1. Inspect the actual input, not just its filename: DOCX contains word/document.xml; PPTX contains ppt/presentation.xml; PDF starts with %PDF-; Markdown and HTML are text. If the extension disagrees with the contents, process the actual format and save the result with its correct extension without overwriting the original. If the user requests a new artifact, use its requested output format. For a legacy, scanned, or unrecognized file, identify a safe editable source or conversion path before editing.
2. Identify the required citation style, bibliography order, managed citation fields, and every in-text number. Map each number to exactly one source; repeated citations share the same target. Do not invent sources or guess an ambiguous match. Preserve brackets, punctuation, and the established numbering rules. For Chinese academic prose using the user's superscript numeric style, make both the complete in-text marker (brackets, numbers, and separators) and each bibliography entry's bracketed number label true superscripts. Apply another baseline or reference-list style only when the user's school, journal, or template requires it.

## Apply by format

- **DOCX/Word:** Preserve Zotero, EndNote, or other managed fields and use that manager's update/link workflow. Otherwise bookmark each bibliography entry and insert a hyperlinked Word cross-reference of type **paragraph number**, not paragraph text. Use real list numbering and dynamic fields when renumbering is expected. For typed labels that cannot safely be converted, link the visible number to its entry bookmark and update displayed numbers after any reorder. When superscript style is required, apply Word's actual superscript formatting to every run of each complete in-text citation marker, including linked number runs, and to the bracketed number label at the start of each bibliography entry. Keep the reference text after that label at the baseline; do not merely reduce font size or raise only some digits. Use the documents skill for DOCX authoring and visual verification.
- **PPTX/PowerPoint:** Treat each visible citation number, including numbers within a group, as independently clickable text or a shape. PowerPoint's ordinary internal link targets a **slide**, not an individual reference row. Link to a shared references slide only when page-level navigation meets the request; for exact per-reference navigation, use a dedicated appendix slide for each cited source. Preserve the slide's typography and layout, and assess the added slide count before changing a large deck. Use the presentations skill to edit and render the PPTX.
- **Markdown/HTML:** Give each reference a stable id and link each visible superscript number to that id, for example <sup>[<a href="#ref-smith-2024">1</a>]</sup> and <li id="ref-smith-2024"><sup>[1]</sup> Reference</li> when the bibliography labels also need superscripts.
- **PDF:** Prefer adding links in the editable source, then export and verify the PDF. For a PDF-only input, inspect whether text and link annotations can be edited reliably; use the PDF skill and do not claim a scanned image has working citation links.

A range such as [5–7] has no visible 6 to click. Follow the required style; expand to [5,6,7] with separate links only when every source must be directly clickable. If that conflicts with a required range style, ask which requirement takes priority.

## Verify

Check every number-to-source mapping, including repeated and grouped citations, after editing or renumbering. For Chinese prose using the user's superscript style, verify that every complete in-text marker and every bibliography number label is superscript, while reference text remains at the baseline. Test representative links in Word, PowerPoint Slide Show, or the final browser/PDF viewer as applicable. Confirm that any exported PDF retained the links and that typography and layout remain intact. Report a PPTX link to a shared references slide as slide-level navigation, never as a jump to a specific row.

This skill handles navigation and numbering. Use the paper-ai skill separately when the task also requires finding sources or checking whether a source supports a claim.
