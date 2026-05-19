# User-Level Git Policy

This file applies to everything under `/home/ywh`.

## Git Rule

For all repositories under `/home/ywh/projects`, use **Windows Git / PowerShell** for Git operations.
Do **not** use WSL Git for project Git work.

This applies to:
- `git status`
- `git add`
- `git commit`
- `git branch`
- `git rebase`
- `git merge`
- `git remote`
- `git fetch`
- `git pull`
- `git push`

## Required Pattern

Always run Git from Windows against the WSL path, for example:

```powershell
git -C "\\wsl.localhost\Ubuntu\home\ywh\projects\ai-trading-assistant" status
git -C "\\wsl.localhost\Ubuntu\home\ywh\projects\ai-trading-assistant" commit -m "..."
git -C "\\wsl.localhost\Ubuntu\home\ywh\projects\ai-trading-assistant" push -u origin main
```

## Remote Preference

Prefer HTTPS remotes for GitHub unless the user explicitly asks for SSH.

## Notes

WSL shell commands are still fine for:
- starting services
- running tests
- reading files
- inspecting local state

But Git operations themselves should go through Windows.
