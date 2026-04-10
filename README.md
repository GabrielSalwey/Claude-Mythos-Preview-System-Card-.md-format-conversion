# Claude Mythos Preview System Card — Markdown Conversion

> **Original document:** [Claude Mythos Preview System Card](https://www.anthropic.com/research/claude-mythos-preview-system-card)
> (Anthropic, April 7, 2026) — 245 pages, PDF
>
> **Copyright in the original belongs to Anthropic PBC. This repository makes
> no copyright claim over that content.** This is an unofficial format
> conversion, not affiliated with or endorsed by Anthropic.

---

The original System Card is a PDF, which makes it harder to search, quote,
reference, and use in LLM-based workflows. This conversion is intended to
make the document more accessible for AI safety researchers, AI welfare
researchers, and anyone working with the evaluations of Claude Mythos Preview.

If you just want to read the document, use the original PDF linked above.
This repo is for people who need machine-readable text.

## What's in this repo

- **`Claude_Mythos_Preview_System_Card.md`** — full converted document
  (~507K chars, ~3,900 lines), including written descriptions of all 81 figures

## Conversion process

Conversion used **[pymupdf4llm](https://pymupdf4llm.readthedocs.io/)** v1.27.2,
a lightweight library designed for producing LLM-ready markdown from PDFs.
The core conversion is three lines of Python; it handled paragraph joining,
heading detection from font size/weight, italic/bold preservation, and table
rendering out of the box. Light post-processing fixed ligatures (`ﬁ` → `fi`),
corrected heading levels based on section numbering depth, removed page number
artifacts, and patched six stuck footnote superscripts.

All 81 figures were described manually: each page containing a figure was
rasterized at 150 DPI using `pdftoppm`, then inspected using Claude Opus 4.6's
vision capability. Descriptions appear as `> **[Visual: ...]**` blockquotes
after each figure caption and include chart type, axis labels, values where
readable, model comparisons, and key takeaways. This was the most labor-intensive
part of the conversion.

## Known limitations

- Figures are described in text, not embedded as images
- Some complex nested tables may have lost structure
- Footnotes appear inline rather than as proper markdown references
- Hyperlinks from the original PDF are only partially preserved

## Copyright and takedown

The content of this document is Anthropic's. This repository provides only
a format conversion for research accessibility purposes, with no commercial
intent. If Anthropic requests removal, this repository will be taken down
promptly. Please open an issue or contact [your email] to flag any concerns.
