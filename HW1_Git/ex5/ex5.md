(base) samng@Sam-MacBook advanced-git-exercises % git checkout exercise5
hello.txt: needs merge
error: you need to resolve your current index first
(base) samng@Sam-MacBook advanced-git-exercises % git reset --hard HEAD^
HEAD is now at 768fa0e commit change merge branch 'exercise3' into exercise4
(base) samng@Sam-MacBook advanced-git-exercises % git merge mundo
Updating 768fa0e..9b96cfd
Fast-forward
 hello.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
(base) samng@Sam-MacBook advanced-git-exercises % cat hello.txt
Hello Mundo!
This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises %  git checkout exercise5
branch 'exercise5' set up to track 'origin/exercise5'.
Switched to a new branch 'exercise5'
(base) samng@Sam-MacBook advanced-git-exercises % cat hello.txt
[greeting] [noun]!
This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git mv hello.txt hello.template

fatal: bad source, source=hello.txt, destination=hello.template
(base) samng@Sam-MacBook advanced-git-exercises %  git add hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git commit
[exercise5 c991682] Replacing greeting with tokens for i18n
 1 file changed, 2 insertions(+)
 create mode 100644 hello.template
(base) samng@Sam-MacBook advanced-git-exercises % git log --since="yesterday"
commit c991682dc2aeb01794827ed695af1040c125b02d (HEAD -> exercise5)
Author: nngsam <11203041@st.neu.edu.vn>
Date:   Sun Aug 27 17:50:47 2023 +0700

    Replacing greeting with tokens for i18n
    
    Currently, hello.txt contains both Spanish and English.
    Let's replace Hola with a [greeting] token, and Mundo
    with a [noun] token. That way, we can localize hello.txt for
    any language!
(base) samng@Sam-MacBook advanced-git-exercises % git log --name-status --follow --oneline hello.template
c991682 (HEAD -> exercise5) Replacing greeting with tokens for i18n
C073    hello.txt       hello.template
fec9e7b Changing Hello to Hola
M       hello.txt
afa34a6 Changing World to Mundo
M       hello.txt
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
M       hello.txt
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master) Initial commit
A       hello.txt
(base) samng@Sam-MacBook advanced-git-exercises % git log --grep=i18n --author=nina --since=2.weeks
(base) samng@Sam-MacBook advanced-git-exercises % git log --grep=i18n --author=nngsam --since=2.weeks
commit c991682dc2aeb01794827ed695af1040c125b02d (HEAD -> exercise5)
Author: nngsam <11203041@st.neu.edu.vn>
Date:   Sun Aug 27 17:50:47 2023 +0700

    Replacing greeting with tokens for i18n
    
    Currently, hello.txt contains both Spanish and English.
    Let's replace Hola with a [greeting] token, and Mundo
    with a [noun] token. That way, we can localize hello.txt for
    any language!
(base) samng@Sam-MacBook advanced-git-exercises % git log --diff-filter=R --find-renames
(base) samng@Sam-MacBook advanced-git-exercises % git log --diff-filter=M --oneline
fec9e7b Changing Hello to Hola
afa34a6 Changing World to Mundo
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
(base) samng@Sam-MacBook advanced-git-exercises % git log --grep=i18n --oneline
c991682 (HEAD -> exercise5) Replacing greeting with tokens for i18n
(base) samng@Sam-MacBook advanced-git-exercises % git show c991682
commit c991682dc2aeb01794827ed695af1040c125b02d (HEAD -> exercise5)
Author: nngsam <11203041@st.neu.edu.vn>
Date:   Sun Aug 27 17:50:47 2023 +0700

    Replacing greeting with tokens for i18n
    
    Currently, hello.txt contains both Spanish and English.
    Let's replace Hola with a [greeting] token, and Mundo
    with a [noun] token. That way, we can localize hello.txt for
    any language!

diff --git a/hello.template b/hello.template
new file mode 100644
index 0000000..a6c57ac
--- /dev/null
+++ b/hello.template
@@ -0,0 +1,2 @@
+[greeting] [noun]!
+This is a test of the emergency git-casting system.
(base) samng@Sam-MacBook advanced-git-exercises % git branch --merged master
  master
(base) samng@Sam-MacBook advanced-git-exercises % git show c991682 --stat --oneline
c991682 (HEAD -> exercise5) Replacing greeting with tokens for i18n
 hello.template | 2 ++
 1 file changed, 2 insertions(+)
(base) samng@Sam-MacBook advanced-git-exercises % git branch --merged master
  master
(base) samng@Sam-MacBook advanced-git-exercises % git branch --no-merged master
  exercise2
  exercise3
  exercise4
* exercise5
  mundo