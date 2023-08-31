(base) samng@Sam-MacBook advanced-git-exercises % git checkout master
Switched to branch 'master'
(base) samng@Sam-MacBook advanced-git-exercises % git remote -v
origin	git@github.com:nnja/advanced-git-exercises.git (fetch)
origin	git@github.com:nnja/advanced-git-exercises.git (push)


(base) samng@Sam-MacBook advanced-git-exercises % git remote rename origin upstream
Renaming remote references: 100% (11/11), done.
(base) samng@Sam-MacBook advanced-git-exercises % git remote -v
upstream	git@github.com:nnja/advanced-git-exercises.git (fetch)
upstream	git@github.com:nnja/advanced-git-exercises.git (push)
(base) samng@Sam-MacBook advanced-git-exercises % git remote add origin git@github.com:mhenstell/advanced-git-exercises.git


(base) samng@Sam-MacBook advanced-git-exercises % git remote rm origin

(base) samng@Sam-MacBook advanced-git-exercises % git pull --rebase
Current branch master is up to date.

(base) samng@Sam-MacBook advanced-git-exercises % echo "Change to local repo" > local_change.txt
(base) samng@Sam-MacBook advanced-git-exercises % git checkout -b feature
Switched to a new branch 'feature'
(base) samng@Sam-MacBook advanced-git-exercises % echo "Change to local repo" > local_change.txt
(base) samng@Sam-MacBook advanced-git-exercises % git add local_change.txt
(base) samng@Sam-MacBook advanced-git-exercises %  git commit -m "Change to local repo"
[feature a23c2ae] Change to local repo
 1 file changed, 1 insertion(+)
 create mode 100644 local_change.txt
(base) samng@Sam-MacBook advanced-git-exercises % git pull --rebase upstream master
From github.com:nnja/advanced-git-exercises
 * branch            master     -> FETCH_HEAD
Current branch feature is up to date.
(base) samng@Sam-MacBook advanced-git-exercises % git log --oneline
a23c2ae (HEAD -> feature) Change to local repo
663656d (master) Master has continued to change
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git pull --rebase
There is no tracking information for the current branch.
Please specify which branch you want to rebase against.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=upstream/<branch> feature