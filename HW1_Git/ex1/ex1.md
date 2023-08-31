(base) samng@Sam-MacBook ~ % mkdir -p ~/HW_DSLab/HW1_Git
(base) samng@Sam-MacBook ~ % cd ~//HW_DSLab/HW1_Git
(base) samng@Sam-MacBook HW1_Git % cd
(base) samng@Sam-MacBook ~ % mkdir -p ~/HW_DSLab/HW0_Git
(base) samng@Sam-MacBook ~ % cd ~/HW_DSLab/HW0_Git

(base) samng@Sam-MacBook HW0_Git % git status
On branch exercise4
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:
	modified:   ../HW1_Git/ex1/hello.txt
	new file:   ../HW1_Git/ex2/hello copy.txt
	new file:   ../HW1_Git/ex3/dangle.txt
	new file:   ../HW1_Git/ex3/hello.txt

Unmerged paths:
  (use "git add <file>..." to mark resolution)
	both modified:   ../HW1_Git/.DS_Store

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	deleted:    ../HW1_Git/ex1/hello.txt
	deleted:    ../HW1_Git/ex2/hello copy.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	../HW1_Git/ex1/hello.template

(base) samng@Sam-MacBook HW0_Git % git status
On branch exercise4
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:
	modified:   ../HW1_Git/ex1/hello.txt
	new file:   ../HW1_Git/ex2/hello copy.txt
	new file:   ../HW1_Git/ex3/dangle.txt
	new file:   ../HW1_Git/ex3/hello.txt

Unmerged paths:
  (use "git add <file>..." to mark resolution)
	both modified:   ../HW1_Git/.DS_Store

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   ../.DS_Store
	deleted:    ../HW1_Git/ex1/hello.txt
	deleted:    ../HW1_Git/ex2/execution.md
	deleted:    ../HW1_Git/ex2/hello copy.txt
	deleted:    ../HW1_Git/ex2/hello.txt
	deleted:    ../HW1_Git/ex3/dangle.txt
	deleted:    ../HW1_Git/ex3/hello.txt
	deleted:    ../README.md

(base) samng@Sam-MacBook HW0_Git % git status
fatal: Unable to read current working directory: Operation not permitted
(base) samng@Sam-MacBook HW0_Git % cd 
(base) samng@Sam-MacBook ~ % mkdir -p ~/DSLab_HW/HW0_Git
(base) samng@Sam-MacBook ~ % cd ~/DSLab_HW/HW0_Git

(base) samng@Sam-MacBook HW0_Git % git status
fatal: not a git repository (or any of the parent directories): .git
(base) samng@Sam-MacBook HW0_Git % git init
Initialized empty Git repository in /Users/samng/DSLab_HW/HW0_Git/.git/
(base) samng@Sam-MacBook HW0_Git % git add README.md
fatal: pathspec 'README.md' did not match any files
(base) samng@Sam-MacBook HW0_Git % echo "DSLab Homeworks" >> README.md
(base) samng@Sam-MacBook HW0_Git % git add README.md
(base) samng@Sam-MacBook HW0_Git % git commit -m "first commit"
[main (root-commit) bc79d20] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
(base) samng@Sam-MacBook HW0_Git % git branch -M main
(base) samng@Sam-MacBook HW0_Git % git remote add origin git@github.com:nngsam/DSLab-HW.git
(base) samng@Sam-MacBook HW0_Git % git push -u origin main
To github.com:nngsam/DSLab-HW.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:nngsam/DSLab-HW.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
(base) samng@Sam-MacBook HW0_Git % git pull origin main
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 588 bytes | 147.00 KiB/s, done.
From github.com:nngsam/DSLab-HW
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> origin/main
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint: 
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint: 
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches.
(base) samng@Sam-MacBook HW0_Git % git push origin main
To github.com:nngsam/DSLab-HW.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'github.com:nngsam/DSLab-HW.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
(base) samng@Sam-MacBook HW0_Git % git push --force origin master
error: src refspec master does not match any
error: failed to push some refs to 'github.com:nngsam/DSLab-HW.git'
(base) samng@Sam-MacBook HW0_Git % git push --force origin main  
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 226 bytes | 226.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:nngsam/DSLab-HW.git
 + dc7de91...bc79d20 main -> main (forced update)
(base) samng@Sam-MacBook HW0_Git % echo 'Hello World!' > hello.txt
(base) samng@Sam-MacBook HW0_Git % git add hello.txt
(base) samng@Sam-MacBook HW0_Git % git commit -m "Initial commit"
[main 3c6c726] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 hello.txt
(base) samng@Sam-MacBook HW0_Git % git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 288 bytes | 288.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:nngsam/DSLab-HW.git
   bc79d20..3c6c726  main -> main
(base) samng@Sam-MacBook HW0_Git % tree .git        
.git
├── COMMIT_EDITMSG
├── FETCH_HEAD
├── HEAD
├── config
├── description
├── hooks
│   ├── applypatch-msg.sample
│   ├── commit-msg.sample
│   ├── fsmonitor-watchman.sample
│   ├── post-update.sample
│   ├── pre-applypatch.sample
│   ├── pre-commit.sample
│   ├── pre-merge-commit.sample
│   ├── pre-push.sample
│   ├── pre-rebase.sample
│   ├── pre-receive.sample
│   ├── prepare-commit-msg.sample
│   ├── push-to-checkout.sample
│   └── update.sample
├── index
├── info
│   └── exclude
├── logs
│   ├── HEAD
│   └── refs
│       ├── heads
│       │   └── main
│       └── remotes
│           └── origin
│               └── main
├── objects
│   ├── 3c
│   │   └── 6c726735bda16a921ae44b2f6e0e278425df07
│   ├── 98
│   │   └── 0a0d5f19a64b4b30a87d4206aade58726b60e3
│   ├── 9f
│   │   └── 1c64dd10e29998610b9dfe7d71650af1f6333b
│   ├── b6
│   │   └── 8e2ef3abe19c7048b95c64041311cf78becade
│   ├── bc
│   │   └── 79d20ab9665d4cf65ffe6cea7e16ad0447e515
│   ├── c1
│   │   └── b8da1c8e2d4c5e498f3e57db47cfd451765d17
│   ├── c5
│   │   └── a3e395c4efa9d4508631346dea064dcdd36d88
│   ├── d0
│   │   └── 86a6025888bbe845f6be670f8c9922805ef82e
│   ├── dc
│   │   └── 7de910e3c96bd34a43a099876a8fd9624a596b
│   ├── info
│   └── pack
└── refs
    ├── heads
    │   └── main
    ├── remotes
    │   └── origin
    │       └── main
    └── tags

25 directories, 34 files
(base) samng@Sam-MacBook HW0_Git % cat .git/HEAD
ref: refs/heads/main
(base) samng@Sam-MacBook HW0_Git % cat .git/refs/heads/master
cat: .git/refs/heads/master: No such file or directory
(base) samng@Sam-MacBook HW0_Git % cat .git/refs/heads/main  
3c6c726735bda16a921ae44b2f6e0e278425df07
(base) samng@Sam-MacBook HW0_Git % git log --oneline
3c6c726 (HEAD -> main, origin/main) Initial commit
bc79d20 first commit