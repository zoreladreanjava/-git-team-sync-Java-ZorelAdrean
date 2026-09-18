# Git Workflow Notes

## Rejected Pushes

The rejected push reported a non-fast-forward update: the remote branch contained commits that were not present locally. It happened because another branch update had already been pushed to the remote, so the local branch was behind and Git would not allow the push to overwrite or discard that remote history.

## Merge Versus Rebase

The merge resolution brought the remote `main` history into the local branch and created a merge commit. A rebase would instead replay the local commits on top of the updated remote base, producing a linear history with new commit IDs. Merge preserves the original branch structure; rebase rewrites the local commits as if they were made after the remote commits.

## One Habit That Would Have Prevented Both Rejections

Before every push, fetch or pull the target branch and check whether the remote has moved. Keeping the local branch current before starting work and before pushing would have avoided both rejected pushes in this lab.

## Default on a Shared Team Branch

I would default to merge on a shared team branch because it preserves published commit history and does not rewrite commits that teammates may already have based work on. Rebase is useful for cleaning up private, unpublished work, but merge is the safer default for shared history.