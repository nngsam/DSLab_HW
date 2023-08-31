```

(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise6
branch 'exercise6' set up to track 'origin/exercise6'.
Switched to a new branch 'exercise6'
(base) samng@Sam-MacBook advanced-git-exercises % echo "Bad data" > hello.template
(base) samng@Sam-MacBook advanced-git-exercises % cat hello.template

Bad data
(base) samng@Sam-MacBook advanced-git-exercises % git checkout -- hello.template
(base) samng@Sam-MacBook advanced-git-exercises % cat hello.template
[greeting] [noun]!
This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git log --name-status --follow --oneline hello.template
4b2b90e (HEAD -> exercise6, origin/exercise6) Replacing greeting with tokens for i18n
R073    hello.txt       hello.template
fec9e7b Changing Hello to Hola
M       hello.txt
afa34a6 Changing World to Mundo
M       hello.txt
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
M       hello.txt
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master) Initial commit
A       hello.txt
(base) samng@Sam-MacBook advanced-git-exercises % git reset HEAD hello.txt
(base) samng@Sam-MacBook advanced-git-exercises % git rm hello.template
rm 'hello.template'
(base) samng@Sam-MacBook advanced-git-exercises % git status
On branch exercise6
Your branch is up to date with 'origin/exercise6'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	deleted:    hello.template

(base) samng@Sam-MacBook advanced-git-exercises % git commit -m "Deleting hello.template"
[exercise6 c3b8778] Deleting hello.template
 1 file changed, 2 deletions(-)
 delete mode 100644 hello.template
(base) samng@Sam-MacBook advanced-git-exercises %  git log --diff-filter=D --oneline -- hello.template
c3b8778 (HEAD -> exercise6) Deleting hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git checkout 7c3b8778^ -- hello.template

fatal: invalid reference: 7c3b8778^
(base) samng@Sam-MacBook advanced-git-exercises % git checkout c3b8778^ -- hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git status
On branch exercise6
Your branch is ahead of 'origin/exercise6' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   hello.template

(base) samng@Sam-MacBook advanced-git-exercises % cat hello.template
[greeting] [noun]!
This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git clean --dry-run
(base) samng@Sam-MacBook advanced-git-exercises % git clean -f
(base) samng@Sam-MacBook advanced-git-exercises % git status
On branch exercise6
Your branch is ahead of 'origin/exercise6' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   hello.template

(base) samng@Sam-MacBook advanced-git-exercises % git reset -- hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git status
On branch exercise6
Your branch is ahead of 'origin/exercise6' by 1 commit.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	hello.template

nothing added to commit but untracked files present (use "git add" to track)
(base) samng@Sam-MacBook advanced-git-exercises % git log --oneline
c3b8778 (HEAD -> exercise6) Deleting hello.template
4b2b90e (origin/exercise6) Replacing greeting with tokens for i18n
ff91b70 (origin/exercise5) Merging in mundo branch
fec9e7b Changing Hello to Hola
4582f72 Merge branch 'exercise3' into exercise4
afa34a6 Changing World to Mundo
7ea8b01 Merge branch 'exercise3' into exercise4
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % rm hello.template
(base) samng@Sam-MacBook advanced-git-exercises % cat hello.template
cat: hello.template: No such file or directory
(base) samng@Sam-MacBook advanced-git-exercises % git reset 4b2b90e -- hello.template
Unstaged changes after reset:
D	hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git status
On branch exercise6
Your branch is ahead of 'origin/exercise6' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   hello.template

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	deleted:    hello.template

(base) samng@Sam-MacBook advanced-git-exercises % cat hello.template
cat: hello.template: No such file or directory
(base) samng@Sam-MacBook advanced-git-exercises % git reset --hard HEAD
HEAD is now at c3b8778 Deleting hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git log -2 --oneline
c3b8778 (HEAD -> exercise6) Deleting hello.template
4b2b90e (origin/exercise6) Replacing greeting with tokens for i18n
(base) samng@Sam-MacBook advanced-git-exercises % git reset 4b2b90e
Unstaged changes after reset:
D	hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git log -1 --oneline
4b2b90e (HEAD -> exercise6, origin/exercise6) Replacing greeting with tokens for i18n
(base) samng@Sam-MacBook advanced-git-exercises % git reset ORIG_HEAD
(base) samng@Sam-MacBook advanced-git-exercises % git log -1 --oneline
c3b8778 (HEAD -> exercise6) Deleting hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git log -1 --oneline
c3b8778 (HEAD -> exercise6) Deleting hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git revert 713f6a1
fatal: bad revision '713f6a1'
(base) samng@Sam-MacBook advanced-git-exercises % git revert c3b8778
[exercise6 2105ad0] Revert "Deleting hello.template"
 1 file changed, 2 insertions(+)
 create mode 100644 hello.template

```
