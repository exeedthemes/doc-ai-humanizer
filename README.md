# VERIFY.AI // Document AI Analysis & Academic Integrity Guard

A browser-based dashboard for reviewing AI-like writing patterns, readability, formulaic phrasing, and local document similarity. The app is intended for educational review, drafting support, citation hygiene, and academic-integrity self-checks.

## Key Features

- **Explainable AI-likeness estimator**: Scores sentence variation, vocabulary range, passive voice, repeated transitions, formulaic phrases, paragraph symmetry, and repeated sentence openers.
- **Confidence level**: Labels short samples as lower-confidence so scores are not over-interpreted.
- **Writing-quality feedback**: Gives concrete revision suggestions for clarity, specificity, readability, and source-aware phrasing.
- **Formulaic phrase scanner**: Highlights overused academic phrases that can make writing sound generic or over-polished.
- **Revision diff view**: Produces a clarity-focused rewrite and shows before/after changes.
- **Large-document revision**: Processes long documents in responsive chunks while preserving the full revised output for copy/download. The diff panel shows a preview for very large files to keep the browser responsive.
- **Similarity scan modes**: Uses public-source lookup through Wikipedia Search and Crossref metadata by default, with a local offline phrase-similarity option available.
- **Broad document import**: Supports `.docx`, `.pdf`, `.txt`, Markdown, RTF, HTML, CSV, TSV, and JSON files in the main editor and local comparison checker.
- **Local reference document checker**: Compares a draft against an uploaded reference using weighted 4-9 word phrase overlap and highlighted matches.
- **Integrity checklist**: Reminds users to verify citations, disclose AI assistance where required, and keep drafts or notes.
- **Report export**: Downloads a JSON report with scores, explanation drivers, feedback, and checklist items.
- **Light/dark theme**: Includes a saved light-mode toggle for brighter editing environments.

## Important Limits

This project is a local heuristic estimator. It does not access Turnitin, SafeAssign, institutional repositories, private detector models, or any external academic database. Results are not proof of authorship, misconduct, plagiarism, or originality.

AI-detection scores should be treated as writing-pattern clues. Formal human writing can produce AI-like signals, and AI-generated writing can avoid obvious signals. Use the report to improve transparency, source support, and writing quality.

## How It Works

The AI-likeness score combines multiple local signals:

1. **Sentence variation**: Measures whether sentence lengths are unusually uniform.
2. **Vocabulary range**: Estimates lexical diversity, repetition, long-word density, and punctuation variety.
3. **Formulaic language**: Counts repeated stock academic transitions and phrases.
4. **Passive voice**: Flags likely passive constructions that may reduce clarity.
5. **Repeated openers**: Detects repeated first words across sentences.
6. **Paragraph symmetry**: Checks whether paragraph lengths are unusually even.
7. **Confidence**: Pulls short samples toward uncertainty instead of making strong claims.

Public-source lookup samples high-value sentences across short and long documents, including beginning, middle, and ending sections for continuity. It returns clickable source links and citation text where public metadata is available. The local similarity checker compares uploaded reference material against the current draft using longer phrase spans. Longer contiguous overlaps carry more weight than isolated common phrases.

## Getting Started

Open the app directly in a browser or run a local static server:

```bash
python3 -m http.server 8000
```

Then visit:

```text
http://localhost:8000
```

Use **Load AI Sample** to try the built-in sample, then run **Analyze & Check Plagiarism** to view the analysis report. Upload a reference document in the Similarity Scan tab to test local phrase-overlap highlighting.
