---
description: Clean up merged git worktrees and branches
---

Clean up git worktrees and branches after PR merges. This command:

1. Lists all current worktrees
2. For each worktree (except main):
   - Checks if the branch has been merged to main
   - If merged:
     - Removes the worktree directory
     - Deletes the local branch
     - Deletes the remote branch (if it exists)
   - If not merged:
     - Shows the branch status and asks if you want to keep it

3. Updates main branch to get latest merged changes
4. Shows summary of what was cleaned up

**Safety features:**

- Never touches main branch or worktree
- Asks for confirmation before deleting unmerged branches
- Provides clear status of what's being kept vs deleted
- Updates main to reflect current remote state

Run this after merging PRs to keep your workspace clean and organized.
