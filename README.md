# 20230502git

## Exercise 1

1. Create a new repository on github
	- with a README.md + LICENCE + .gitigore
2. `clone` the repository to your computer
	- usually somewhere in `~/git`
3. In the `README.md` file define `git clone` and `git init`
4. `git add` and `git commit` your changes
5. `git push` your changes back up to your github repository

## Creating a local repository

- `git clone <URL>`: "downloads" the repository to the current directory
- `git init`: initializes the current directory as a git repo

## Branches

- `git branch <NAME>`: creates a branch where HEAD is
- `git branch -a`: lists all the branches
- `git switch <NAME>`: moves HEAD / switches your branch to <NAME>
  - `git checkout <NAME>` older way to switch branches

## Exercise 2

- create a branch `branch_defs`
- edit README
	- `git log --oneline --graph --all`
	- `git push`
	- pull request
- add/commit changes
- push branch
- create the PR
- merge the PR
- sync our local `main` with `orign/main`
- `fetch --prune`
- delete local branch

## Merging branches via PR

- `git log --oneline --graph --all`: show you a decorated history
- `git push <REMOTE> <BRANCH>`: push a branch to the remote, pay attention to what branch you're working on

## Clean up branches + history

- `git fetch`: updates the git log / history
  - `git fetch --prune`: deletes any remote branches that were deleted
- `git branch -d <NAME>`: delete branch on your local machine

- pull requests will auto update when you push the branch again

## Rebase

- `git fetch --prune`
- `git switch main`
- `git pull origin main`
- `git switch <BRANCH>`
- `git rebase main`: command to incorporate main into current branch

Code to simulate conflicts:

```bash
git checkout -b conflict_branch_1
echo "Changes to b1 commit 1" >> README.md
git status
git add README.md
git commit -m "b1 c1"
echo "Changes to b1 commit 2" >> README.md
git add README.md
git commit -m "b1 c2"
git checkout main
git checkout -b conflict_branch_2
echo "Changes to b2 commit 1" >> README.md
git add README.md
git commit -m "b2 c1"
echo "Changes to b2 commit 2" >> README.md
git add README.md
git commit -m "b2 c2"
git push origin conflict_branch_2
git push origin conflict_branch_1
```
Changes to b1 commit 1
