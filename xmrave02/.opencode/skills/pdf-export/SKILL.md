---
name: pdf-export
description: Converts markdown files to PDF using pandoc with LaTeX
---

# PDF Generation Skill

Converts markdown files to PDF using pandoc with LaTeX.

## Usage

When user asks to export/convert markdown to PDF:

1. Check if pandoc is available: `which pandoc`
2. Run pandoc with LaTeX engine:
   ```bash
   pandoc "input.md" -o "output.pdf" --pdf-engine=pdflatex -V geometry:margin=2.5cm -V fontsize=11pt
   ```

## Common Issues

- **Unicode emojis in tables**: Replace emojis (✅, ❌, etc.) with text ("schvaleno", "zamitnuto") before PDF generation
- **Large tables**: May trigger "Float too large" warnings - acceptable
- **UTF-8 link warnings**: Non-breaking warnings, ignore

## Output

PDF file created in same directory as source markdown.
