(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise4
branch 'exercise4' set up to track 'origin/exercise4'.
Switched to a new branch 'exercise4'
(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise4

Already on 'exercise4'
Your branch is up to date with 'origin/exercise4'.
(base) samng@Sam-MacBook advanced-git-exercises % git merge exercise3
Updating 43388fe..e348ebc
Fast-forward
 hello.txt | 1 +
 1 file changed, 1 insertion(+)
(base) samng@Sam-MacBook advanced-git-exercises % git log --oneline
e348ebc (HEAD -> exercise4, tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git reset --hard HEAD^
HEAD is now at 43388fe Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git merge --no-ff exercise3
Merge made by the 'ort' strategy.
 hello.txt | 1 +
 1 file changed, 1 insertion(+)
(base) samng@Sam-MacBook advanced-git-exercises % git log --graph
*   commit 768fa0ef0fdd79adc0861cce3bc0afa68c42b1e3 (HEAD -> exercise4)
|\  Merge: 43388fe e348ebc
| | Author: nngsam <11203041@st.neu.edu.vn>
| | Date:   Sun Aug 27 17:31:15 2023 +0700
| | 
| |     commit change merge branch 'exercise3' into exercise4
| | 
| * commit e348ebc1187cb3b4066b1e9432a614b464bf9d07 (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3)
|/  Author: Nina Zakharenko <nina@nnja.io>
|   Date:   Wed Oct 4 19:01:12 2017 -0700
|   
|       Testing the emergency git-casting system
| 
* commit 43388fee19744e8893467331d7853a6475a227b8 (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master)
  Author: Nina Zakharenko <nina@nnja.io>
  Date:   Wed Oct 4 18:51:49 2017 -0700
  
      Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git branch
  exercise2
  exercise3
* exercise4
  master
(base) samng@Sam-MacBook advanced-git-exercises % git checkout -b mundo
Switched to a new branch 'mundo'
(base) samng@Sam-MacBook advanced-git-exercises % git branch
  exercise2
  exercise3
  exercise4
  master
* mundo
(base) samng@Sam-MacBook advanced-git-exercises % # Edit your hello.txt to say "Hello Mundo!"
dquote> 
(base) samng@Sam-MacBook advanced-git-exercises % git status
On branch mundo
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   hello.txt

no changes added to commit (use "git add" and/or "git commit -a")
(base) samng@Sam-MacBook advanced-git-exercises % git add hello.txt
(base) samng@Sam-MacBook advanced-git-exercises % git commit -m "Changing World to Mundo"
[mundo 9b96cfd] Changing World to Mundo
 1 file changed, 1 insertion(+), 1 deletion(-)
(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise 4
error: pathspec 'exercise' did not match any file(s) known to git
error: pathspec '4' did not match any file(s) known to git
(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise4
Switched to branch 'exercise4'
Your branch is ahead of 'origin/exercise4' by 2 commits.
  (use "git push" to publish your local commits)
(base) samng@Sam-MacBook advanced-git-exercises % git push
ERROR: Permission to nnja/advanced-git-exercises.git denied to nngsam.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
(base) samng@Sam-MacBook advanced-git-exercises % git push --force         
ERROR: Permission to nnja/advanced-git-exercises.git denied to nngsam.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
(base) samng@Sam-MacBook advanced-git-exercises % git push origin exercise4 
ERROR: Permission to nnja/advanced-git-exercises.git denied to nngsam.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
(base) samng@Sam-MacBook advanced-git-exercises % git config user.name
nngsam
(base) samng@Sam-MacBook advanced-git-exercises % git config user.email
11203041@st.neu.edu.vn
(base) samng@Sam-MacBook advanced-git-exercises %  git add hello.txt
(base) samng@Sam-MacBook advanced-git-exercises % git commit -m "Changing Hello to Hola"
[exercise4 5448b57] Changing Hello to Hola
 1 file changed, 1 insertion(+), 1 deletion(-)
(base) samng@Sam-MacBook advanced-git-exercises % git config rerere.enabled true

(base) samng@Sam-MacBook advanced-git-exercises %  git merge mundo
Auto-merging hello.txt
CONFLICT (content): Merge conflict in hello.txt
Recorded preimage for 'hello.txt'
Automatic merge failed; fix conflicts and then commit the result.
(base) samng@Sam-MacBook advanced-git-exercises % git rerere diff
--- a/hello.txt
+++ b/hello.txt
@@ -1,6 +1,6 @@
-<<<<<<<
-Hello Mundo!
-=======
+<<<<<<< HEAD
 Hola World!
->>>>>>>
+=======
+Hello Mundo!
+>>>>>>> mundo
 This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git rerere diff
--- a/hello.txt
+++ b/hello.txt
@@ -1,6 +1,6 @@
-<<<<<<<
-Hello Mundo!
-=======
+<<<<<<< HEAD
 Hola World!
->>>>>>>
+=======
+Hello Mundo!
+>>>>>>> mundo
 This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git add hello.txt
(base) samng@Sam-MacBook advanced-git-exercises % git commit -m "Merging in mundo branch"
Recorded preimage for 'hello.txt'
[exercise4 abaa13a] Merging in mundo branch
(base) samng@Sam-MacBook advanced-git-exercises % git reset --hard HEAD^
HEAD is now at 5448b57 Changing Hello to Hola
(base) samng@Sam-MacBook advanced-git-exercises % git merge mundo
Auto-merging hello.txt
CONFLICT (content): Merge conflict in hello.txt
Recorded preimage for 'hello.txt'
Automatic merge failed; fix conflicts and then commit the result.
(base) samng@Sam-MacBook advanced-git-exercises % cat hello.txt
<<<<<<< HEAD
Hola World!
=======
Hello Mundo!
>>>>>>> mundo
This is a test of the emergency git-casting system.