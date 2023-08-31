```
(base) samng@Sam-MacBook ~ % mkdir -p ~/HW_DSLab/HW0_Git
(base) samng@Sam-MacBook ~ % cd ~/HW_DSLab/HW0_Git
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
```
