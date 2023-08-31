```
(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise9
branch 'exercise9' set up to track 'upstream/exercise9'.
Switched to a new branch 'exercise9'
(base) samng@Sam-MacBook advanced-git-exercises % git grep -e "Python"
python_code.py:# This is a Python file
python_code.py:    print("Welcome to Python!")
(base) samng@Sam-MacBook advanced-git-exercises % git grep --line-number --heading --break -e "Python"
python_code.py
1:# This is a Python file
4:    print("Welcome to Python!")
(base) samng@Sam-MacBook advanced-git-exercises % echo "More Python code" >> python_code.py
(base) samng@Sam-MacBook advanced-git-exercises % git grep --line-number -e "Python"
python_code.py:1:# This is a Python file
python_code.py:4:    print("Welcome to Python!")
python_code.py:5:More Python code
(base) samng@Sam-MacBook advanced-git-exercises % git grep --line-number --cached -e "Python"
python_code.py:1:# This is a Python file
python_code.py:4:    print("Welcome to Python!")
(base) samng@Sam-MacBook advanced-git-exercises % git add python_code.py
(base) samng@Sam-MacBook advanced-git-exercises % git grep --line-number --cached -e "Python"
python_code.py:1:# This is a Python file
python_code.py:4:    print("Welcome to Python!")
python_code.py:5:More Python code

# There it is!
Step
dquote> 
(base) samng@Sam-MacBook advanced-git-exercises % git checkout python_code.py
Updated 0 paths from the index
(base) samng@Sam-MacBook advanced-git-exercises % git log --oneline
88f6e28 (HEAD -> exercise9, upstream/exercise9) Adding bash, python, and java code examples
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git log exercise3 --oneline
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, upstream/exercise3, exercise3) Testing the emergency git-casting system
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git cherry-pick e348ebc
error: your local changes would be overwritten by cherry-pick.
hint: commit your changes or stash them to proceed.
fatal: cherry-pick failed
(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise9
M	python_code.py
Already on 'exercise9'
Your branch is up to date with 'upstream/exercise9'.
(base) samng@Sam-MacBook advanced-git-exercises %  git cherry-pick e348ebc
error: your local changes would be overwritten by cherry-pick.
hint: commit your changes or stash them to proceed.
fatal: cherry-pick failed
(base) samng@Sam-MacBook advanced-git-exercises % git stash
Saved working directory and index state WIP on exercise9: 88f6e28 Adding bash, python, and java code examples
(base) samng@Sam-MacBook advanced-git-exercises %  git cherry-pick e348ebc
[exercise9 a2064c4] Testing the emergency git-casting system
 Author: Nina Zakharenko <nina@nnja.io>
 Date: Wed Oct 4 19:01:12 2017 -0700
 1 file changed, 1 insertion(+)
(base) samng@Sam-MacBook advanced-git-exercises % git log --oneline
a2064c4 (HEAD -> exercise9) Testing the emergency git-casting system
88f6e28 (upstream/exercise9) Adding bash, python, and java code examples
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises %  git blame hello.txt
^43388fe (Nina Zakharenko 2017-10-04 18:51:49 -0700 1) Hello World!
a2064c4d (Nina Zakharenko 2017-10-04 19:01:12 -0700 2) This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git rm java_code.java
rm 'java_code.java'
(base) samng@Sam-MacBook advanced-git-exercises % git commit -m "Who uses Java anyway?"
[exercise9 24e4803] Who uses Java anyway?
 1 file changed, 7 deletions(-)
 delete mode 100644 java_code.java
(base) samng@Sam-MacBook advanced-git-exercises % git log --diff-filter=D -- java_code.java
commit 24e48038f44ddad65a397491bc73d77542062e9a (HEAD -> exercise9)
Author: nngsam <11203041@st.neu.edu.vn>
Date:   Sun Aug 27 18:37:52 2023 +0700

    Who uses Java anyway?
(base) samng@Sam-MacBook advanced-git-exercises % git blame 24e48038f44ddad65a397491bc73d77542062e9a^ -- java_code.java
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 1) // This is a Java file
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 2) 
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 3) public class HelloWorld {
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 4)    public static void main(String[] args) {
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 5)       System.out.println("Привет от Java!");
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 6)    }
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 7) }
(base) samng@Sam-MacBook advanced-git-exercises % git log --oneline
24e4803 (HEAD -> exercise9) Who uses Java anyway?
a2064c4 Testing the emergency git-casting system
88f6e28 (upstream/exercise9) Adding bash, python, and java code examples
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD) Initial commit
(base) samng@Sam-MacBook advanced-git-exercises % git bisect start 24e4803 43388fe 
Bisecting: 0 revisions left to test after this (roughly 1 step)
[a2064c4d409e6a36f6ed907704b2861fbefb8e8f] Testing the emergency git-casting system
(base) samng@Sam-MacBook advanced-git-exercises %  cat hello.txt
Hello World!
This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git bisect bad
Bisecting: 0 revisions left to test after this (roughly 0 steps)
[88f6e2864bd0829c71654f1d19096f436a66ce07] Adding bash, python, and java code examples
(base) samng@Sam-MacBook advanced-git-exercises % cat hello.txt
Hello World!
(base) samng@Sam-MacBook advanced-git-exercises % git bisect good

a2064c4d409e6a36f6ed907704b2861fbefb8e8f is the first bad commit
commit a2064c4d409e6a36f6ed907704b2861fbefb8e8f
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:01:12 2017 -0700

    Testing the emergency git-casting system

 hello.txt | 1 +
 1 file changed, 1 insertion(+)
```
