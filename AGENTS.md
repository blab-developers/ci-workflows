# Repo family


## Clone and Worktree Policy

Minimize creation of clones and worktrees: only create them to prevent blocking conflicts or test complex scenarios in isolation. If you do create one, you are responsible for merging any uncommitted changes back to the original checkout and deleting the clone or worktree before concluding your work. Stale clones and worktrees create maintenance burden and confusion.
This is a shared repository: both families (`bidwej-*` on GitHub/Forgejo, `eai-*` on GitHub/GitLab)
call the reusable workflows published here. It is the one place the secret-scan implementation
lives (ADR-0036 amendment); consumers carry callers, not copies. Public so private-repo
boundaries do not block `workflow_call`.
