---
inclusion: fileMatch
fileMatchPattern: "*"
---

# EditorConfig Standards

When creating or editing files, follow these formatting rules derived from the project's `.editorconfig`:

## General Rules (all files)

- Use **spaces** for indentation (not tabs)
- Indent size: **2 spaces**
- Line endings: **LF** (`\n`) — never use CRLF
- Charset: **UTF-8**
- Always **trim trailing whitespace**
- Always **insert a final newline** at the end of files

## Exceptions

### Markdown files (`*.md`)
- Do NOT trim trailing whitespace (trailing spaces can be intentional for line breaks)

### Text files (`*.txt`)
- Do NOT trim trailing whitespace
- Do NOT insert a final newline

### Python files (`*.py`)
- Indent size: **4 spaces** (PEP 8 standard)

### Makefiles (`Makefile`, `*.mk`)
- Use **tabs** for indentation (required by Make syntax)

## Summary

| File type | Indent | Trailing whitespace | Final newline |
|-----------|--------|---------------------|---------------|
| Default   | 2 spaces | Trim              | Yes           |
| `*.py`    | 4 spaces | Trim              | Yes           |
| `*.md`    | 2 spaces | Keep              | Yes           |
| `*.txt`   | 2 spaces | Keep              | No            |
| Makefile  | Tab      | Trim              | Yes           |
