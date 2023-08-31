(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise3
branch 'exercise3' set up to track 'origin/exercise3'.
Switched to a new branch 'exercise3'
(base) samng@Sam-MacBook advanced-git-exercises % cat .git/HEAD
ref: refs/heads/exercise3
(base) samng@Sam-MacBook advanced-git-exercises % git branch

  exercise2
* exercise3
  master
(base) samng@Sam-MacBook advanced-git-exercises % git show-ref --heads
5f9e02dcdc660624749874b75327dad430c82442 refs/heads/exercise2
e348ebc1187cb3b4066b1e9432a614b464bf9d07 refs/heads/exercise3
43388fee19744e8893467331d7853a6475a227b8 refs/heads/master
(base) samng@Sam-MacBook advanced-git-exercises % git cat-file -p 5f9e02dcdc660624749874b75327dad430c82442
tree cbcdf5dda7853d595fe0b1942cb0d1d72eb910f3
parent 43388fee19744e8893467331d7853a6475a227b8
author nngsam <11203041@st.neu.edu.vn> 1693131509 +0700
committer nngsam <11203041@st.neu.edu.vn> 1693131509 +0700

move to ex3
(base) samng@Sam-MacBook advanced-git-exercises % git cat-file -p 43388fee19744e8893467331d7853a6475a227b8
tree 581caa0fe56cf01dc028cc0b089d364993e046b6
author Nina Zakharenko <nina@nnja.io> 1507168309 -0700
committer Nina Zakharenko <nina@nnja.io> 1507168309 -0700

Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git cat-file -p e348ebc1187cb3b4066b1e9432a614b464bf9d07
tree cbcdf5dda7853d595fe0b1942cb0d1d72eb910f3
parent 43388fee19744e8893467331d7853a6475a227b8
author Nina Zakharenko <nina@nnja.io> 1507168872 -0700
committer Nina Zakharenko <nina@nnja.io> 1507168872 -0700

Testing the emergency git-casting system
(base) samng@Sam-MacBook advanced-git-exercises % git tag my-exercise3-tag
(base) samng@Sam-MacBook advanced-git-exercises % git show-ref --tag
e348ebc1187cb3b4066b1e9432a614b464bf9d07 refs/tags/my-exercise3-tag
(base) samng@Sam-MacBook advanced-git-exercises % git tag --points-at e348ebc
my-exercise3-tag
(base) samng@Sam-MacBook advanced-git-exercises % git tag -a "exercise3-annotated-tag" -m "This is my annotated tag for exercise 3"
(base) samng@Sam-MacBook advanced-git-exercises % git show exercise3-annotated-tag
tag exercise3-annotated-tag
Tagger: nngsam <11203041@st.neu.edu.vn>
Date:   Sun Aug 27 17:26:19 2023 +0700

This is my annotated tag for exercise 3

commit e348ebc1187cb3b4066b1e9432a614b464bf9d07 (HEAD -> exercise3, tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3)
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:01:12 2017 -0700

    Testing the emergency git-casting system

diff --git a/hello.txt b/hello.txt
index 980a0d5..b31a35b 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1 +1,2 @@
 Hello World!
+This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git show
commit e348ebc1187cb3b4066b1e9432a614b464bf9d07 (HEAD -> exercise3, tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3)
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:01:12 2017 -0700

    Testing the emergency git-casting system

diff --git a/hello.txt b/hello.txt
index 980a0d5..b31a35b 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1 +1,2 @@
 Hello World!
+This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git log --oneline
e348ebc (HEAD -> exercise3, tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git checkout e348ebc
Note: switching to 'e348ebc'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at e348ebc Testing the emergency git-casting system
(base) samng@Sam-MacBook advanced-git-exercises % cat .git/HEAD

e348ebc1187cb3b4066b1e9432a614b464bf9d07
(base) samng@Sam-MacBook advanced-git-exercises % echo "This is a test file" > dangle.txt
(base) samng@Sam-MacBook advanced-git-exercises % git add dangle.txt
(base) samng@Sam-MacBook advanced-git-exercises % git commit -m "This is a dangling commit"
[detached HEAD cd88311] This is a dangling commit
 1 file changed, 1 insertion(+)
 create mode 100644 dangle.txt
(base) samng@Sam-MacBook advanced-git-exercises % git log --oneline
cd88311 (HEAD) This is a dangling commit
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % cat .git/HEAD
cd88311051b0db937cecae6ae9694128f71a19c9
(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise3
Warning: you are leaving 1 commit behind, not connected to
any of your branches:

  cd88311 This is a dangling commit

If you want to keep it by creating a new branch, this may be a good time
to do so with:

 git branch <new-branch-name> cd88311

Switched to branch 'exercise3'
Your branch is up to date with 'origin/exercise3'.