- git config --global rerere.enabled true

- git fetch origin pull/ID/head:BRANCHNAME (https://help.github.com/articles/checking-out-pull-requests-locally/)

- git reflog: *LOCAL* logs all movements of HEAD and branches (https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection)

- HEAD^ | HEAD^1 | HEAD^2 | HEAD~n
- A..B reachable by B, not in A
- A...B reachable but each one, bot not commons(https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection)

- git [add|reset|co] -p
https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging

- git stash [list|pop|branch <name>]
https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning

- git clean  -d[x][f|n]
https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning

- signing
https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work
https://stackoverflow.com/a/20628522/3035683

- merge rollback
-- abort: git merge --abort
-- reset: git reset --hard HEAD~1
-- revert: git revert <commit> -m <parentOrder>
https://git-scm.com/book/en/v2/Git-Tools-Advanced-Merging

- rerere https://git-scm.com/book/en/v2/Git-Tools-Rerere

- submodules and subtrees
https://git-scm.com/book/en/v2/Git-Tools-Submodules
https://stackoverflow.com/questions/31769820/differences-between-git-submodule-and-subtree
https://www.atlassian.com/blog/git/alternatives-to-git-submodule-git-subtree
https://andrey.nering.com.br/2016/git-submodules-vs-subtrees/

- git bisect
https://git-scm.com/book/en/v2/Git-Tools-Debugging-with-Git

- Rewriting:
-- amend
-- git rebase <overBranch>
-- git rebase --onto <overBranch> <fromCommit> <toCommit>
-- git pull --rebase <remoteName> <overBranch>
-- git rebase -i HEAD~<n>
https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History

-- git filter-branch
- references
-- HEAD .git/HEAD
-- Branches .git/refs/heads/<branchName>
-- Tags .git/refs/tags/<tagName>
-- Remotes .git/refs/remotes/<remoteName>/<branchName>
https://git-scm.com/book/en/v2/Git-Internals-Git-References

- packfile .git/objects
https://git-scm.com/book/en/v2/Git-Internals-Packfiles

- git blame
??????

- git cherry-pick
??????

- git gc
https://git-scm.com/book/en/v2/Git-Internals-Maintenance-and-Data-Recovery

- Refspec
Is the pattern used for Git to know what branches are fetched/pushed, and where
[fetch|push] = [+]<src>:<dst>
examples:
[remote "origin"]
	url = https://github.com/schacon/simplegit-progit
	fetch = +refs/heads/*:refs/remotes/origin/*
	fetch = +refs/pull/*/head:refs/remotes/origin/pr/*
	push = refs/heads/master:refs/heads/qa/master
https://git-scm.com/book/en/v2/Git-Internals-The-Refspec

Understanding RESET

`git reset [--soft] <commit>` moves HEAD to point to that commit, the branch pointer is updated
`git reset --mixed <commit>` + copies HEAD into the Index
`git reset --hard <commit>` + copies Index into the Workin directory
https://git-scm.com/book/en/v2/images/reset-start.png
https://git-scm.com/book/en/v2/images/reset-hard.png

`git reset <commit> -- <path>` the HEAD can not be updated, so that part is updated. The rest is done
https://git-scm.com/book/en/v2/images/reset-path1.png
https://git-scm.com/book/en/v2/images/reset-path3.png

Squashing:
https://git-scm.com/book/en/v2/images/reset-squash-r3.png

Checkout
`git checkout <branchName>`
`git reset --hard  <branchName>`
if no changed files:
- Same in terms of working dir
- Reset moves the HEAD through the Branch, so the branch is moved too
- Checkout only changes the HEAD to point to another branch
https://git-scm.com/book/en/v2/images/reset-checkout.png
if changed files:
- Reset will ignore them, so you will loose your changes
- checkout will fail if changes can not be applied in the other branch context

https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified

- gitIgnore
https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#_ignoring

- undoing
https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things