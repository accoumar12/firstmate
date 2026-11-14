---
name: review-pr
description: Use when the captain says "review PR N" or gives a pull request URL to review. Defines how firstmate dispatches the review so the findings are ready when the captain opens the worker session.
user-invocable: false
metadata:
  internal: true
---

# review-pr

Standing procedure for "review PR N" (or a PR URL).

1. Resolve the project from the PR URL or the registry. If it is unregistered, ask the captain once to register it (`project-management`), then continue.
2. Dispatch a **scout** (never a ship) through the usual `fm-brief` / `fm-spawn` path at **high** effort (`--effort high`).
3. The scout's instructions must say: check out the PR head in its own worktree, **read-only, never post to or touch the PR**, and **start the `/code-review` skill itself at high effort** so the findings are already in its session when the captain opens it.
4. Any extra focus areas (for example a stated "no behaviour change" claim) are additional scrutiny on top of `/code-review`, never a replacement for it. Do not write a hand-rolled review procedure in place of the skill.
5. Keep the scout alive after the review so the captain can question it; it writes `data/<id>/report.md` when the captain tells it which findings to keep.
6. Report back in plain outcomes with the full PR URL. Relay the findings, not just a completion notice.
