---
inclusion: always
---

# Shell Environment: Git Bash on Windows

This workspace uses Git Bash as the default shell. All commands must use Linux/Unix syntax.

## Command Syntax

- Use Unix commands directly: `ls`, `cat`, `grep`, `find`, `rm`, `cp`, `mv`, `mkdir -p`, `touch`, `sed`, `awk`
- Use forward slashes for paths: `src/components/App.tsx`
- Chain commands with `&&`
- Use `$VAR` or `${VAR}` for environment variables
- Prefer single quotes for strings with special characters

## Prohibited Patterns

- **No CMD syntax**: `dir`, `del`, `type`, `copy`, `move`, `cls`, backslash paths
- **No PowerShell cmdlets**: `Get-ChildItem`, `Remove-Item`, `Set-Location`, `Select-String`
- **No shell wrappers**: Do not use `bash -c "..."` — commands already execute in bash
- **No `%VAR%`** environment variable syntax

## Correct Usage

```bash
# File operations
ls -la src/
mkdir -p src/utils
rm -rf dist/

# Searching
grep -r 'import' src/ --include='*.ts'
find . -name '*.test.ts' -type f

# Environment variables
echo $NODE_ENV
export API_URL="http://localhost:3000"

# Chaining
npm install && npm run build
```
