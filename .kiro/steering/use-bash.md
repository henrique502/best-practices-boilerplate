---
inclusion: always
---

# Shell Commands: Use Linux Commands (Git Bash)

The default terminal is Git Bash. Always use Linux/Unix commands directly — never use CMD or PowerShell syntax.

## Rules

- Use Linux/Unix commands directly: ls, cat, grep, find, rm, cp, mv, mkdir -p, touch, etc.
- Do NOT wrap commands in `bash -c "..."`. Run commands directly since the terminal is already bash.
- Use / as path separator instead of \.
- Use && to chain commands.
- Use single quotes for strings containing special characters when possible.
- Environment variables: use $VAR or ${VAR} syntax, not %VAR%.
- Do NOT use PowerShell cmdlets (Get-ChildItem, Remove-Item, etc.).
- Do NOT use CMD commands (dir, del, type, etc.).
- All commands run natively in Git Bash — no need for any shell wrapper.

## Examples

```bash
# Good - direct commands
ls -la src/
cat package.json
grep -r "import" src/ --include="*.ts"
rm -rf build/

# Bad - unnecessary bash -c wrapper
bash -c "ls -la src/"
bash -c "cat package.json"

# Bad - CMD/PowerShell syntax
dir src\
type package.json
Get-ChildItem src/
```
