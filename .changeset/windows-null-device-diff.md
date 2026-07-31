---
"@moonshot-ai/agent-core-v2": patch
---

Fix `GitService.diff` returning an empty diff on Windows for untracked files and files added before the first commit. `/dev/null` resolves to a real filesystem path (not the null device) on native Windows, so `git diff --no-index` was failing silently; the Windows `NUL` device alias is now used instead.
