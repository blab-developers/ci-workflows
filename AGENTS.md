# Repo family

This is a shared repository: both families (`bidwej-*` on GitHub/Forgejo, `eai-*` on GitHub/GitLab)
call the reusable workflows published here. It is the one place the secret-scan implementation
lives (ADR-0036 amendment); consumers carry callers, not copies. Public so private-repo
boundaries do not block `workflow_call`.
