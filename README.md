# pptx__viewing

A Claude Code skill that reads PDF/PPTX slides, renders each page as an image, and generates a well-explained Obsidian Markdown note — with only the most important images included.

## What it does

- Renders every page of a PDF or PPTX to PNG
- Extracts text from all pages to understand the full content first
- **Selects only the important pages** to include as images (not every slide) — the ratio scales with content difficulty: ~30% for easy, ~50% for medium, ~60-70% for hard
- Writes an explanatory note in your own words, not a copy of the slide text
- Cleans up unused images after writing

The output is a proper study note, not a slide dump.

## Install

```bash
npx skills add lyuyao59/pptx-viewing-skill@pptx__viewing
```

## Usage

Just tell Claude Code:

- "帮我看一下这个PPT" + file path
- "把这个课件整理成笔记，放到 [目录]"
- "这个PDF我看不懂，帮我生成图文讲解"

## Requirements

Python with PyMuPDF installed:

```bash
pip install pymupdf
```

For PPTX files, LibreOffice is recommended for conversion:

```bash
# macOS
brew install libreoffice

# Ubuntu/Debian
sudo apt install libreoffice
```

## Output structure

```
输出目录/
├── 文件名_笔记.md        ← the note (Obsidian [[]] image syntax)
└── 文件名_images/
    ├── page_02.png       ← only pages actually referenced in the note
    ├── page_08.png
    └── ...
```

## License

MIT
