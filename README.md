# pandoc-docx-pagebreak-py

Pandoc filter to insert page break or table-of-contents in docx file

### install

```bash
pip3 install git+https://github.com/Cybratech/pandoc-docx-pagebreak-py
```

### Usage

- Add `\newpage` where preferred to insert a page break
    - Expecting to work like native pandoc behavior for latex output
- Add `\toc` where preferred to insert TOC(Table of Contents)
    - unable to use with `--toc` otherwise TOC appears on head of document also

```bash
# Try the filter with this file like this:
pandoc -f markdown -t docx -o docx.docx --filter=pandoc-docx-pagebreakpy README.md
```

### Sample

```markdown
Table of contents appears after this line

\toc

Contents before pagebreak

\newpage

Contents after _Page Break_
```

Table of contents appears after this line

\toc

Contents before pagebreak

\newpage

Contents after _Page Break_

### Renaming the TOC

The default name of the TOC wille be `Inhaltsverzeichnis`. If you want to rename it, you can simply add a meta-info named `toc-name` with a value of the name.

For instance in an markdown-file:

```md
---
title: Document Title
toc-name: <Name to set>
---

\toc

\newpage
```
