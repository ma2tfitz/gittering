# Rebase/Squash example

```bash
mfitzgib$ git init -b main
2024-10-19 12:27:45.453 xcodebuild[40491:64116013] Requested but did not find extension point with identifier Xcode.IDEKit.ExtensionSentinelHostApplications for extension Xcode.DebuggerFoundation.AppExtensionHosts.watchOS of plug-in com.apple.dt.IDEWatchSupportCore
2024-10-19 12:27:45.453 xcodebuild[40491:64116013] Requested but did not find extension point with identifier Xcode.IDEKit.ExtensionPointIdentifierToBundleIdentifier for extension Xcode.DebuggerFoundation.AppExtensionToBundleIdentifierMap.watchOS of plug-in com.apple.dt.IDEWatchSupportCore
Initialized empty Git repository in /Users/mfitzgib/proj/dockerization/.git/
mfitzgib$ git add .
mfitzgib$ git add README.md
mfitzgib$ git commit -m "first commit"
[main (root-commit) 399225e] first commit
 6 files changed, 42 insertions(+)
 create mode 100644 README.md
 create mode 100644 bcl-convert/Dockerfile
 create mode 100644 bcl-convert/README.txt
 create mode 100755 bcl-convert/apptainer-convert.sh
 create mode 100644 bcl-convert/bcl-convert-4.2.7-2.el7.x86_64.rpm
 create mode 100755 bcl-convert/docker-build.sh
mfitzgib$ git branch -M main
mfitzgib$ ssh-add -L
mfitzgib$ git push -u origin main
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 10 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 9.12 MiB | 1.90 MiB/s, done.
Total 9 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:ma2tfitz/dockerization.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
mfitzgib$ emacs .gitignore
mfitzgib$ emacs LICENSE
mfitzgib$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   .gitignore
	new file:   LICENSE

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
pick 479b182 clean up
	modified:   README.md

mfitzgib$ git commit -m 'clean up'
[main 479b182] clean up
 2 files changed, 190 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 LICENSE
mfitzgib$ git push -u origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 10 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 2.48 KiB | 2.48 MiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:ma2tfitz/dockerization.git
   399225e..479b182  main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
mfitzgib$ git commit -m 'more cleanup'
mfitzgib$ git log --pretty=oneline
36a56fe653b9cecc6d35739752475c286065a0ba (HEAD -> main, origin/main) more cleanup
479b182471d9dffeed2dc25c47fa186784d2575b clean up
399225e082b27bac1c88b3c760eb4980c52a0f03 first commit
mfitzgib$ git rebase --interactive HEAD~2
[detached HEAD f05a83c] clean up
 Date: Sat Oct 19 12:51:25 2024 -0700
 3 files changed, 191 insertions(+), 1 deletion(-)
 create mode 100644 .gitignore
 create mode 100644 LICENSE
Successfully rebased and updated refs/heads/main.
mfitzgib$ git log --pretty=oneline
f05a83c9cd617ce0e77f6f78882d172822474811 (HEAD -> main) clean up
399225e082b27bac1c88b3c760eb4980c52a0f03 first commit
```