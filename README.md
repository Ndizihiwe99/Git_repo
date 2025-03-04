# Git_repo
## Part 1: Refining Git History

### 6. Dropping a Commit:

```
gymikirengaii@Ikirengas-iMac Git_repo % git add .
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "Unwanted commit"
[main bd45c8a] Unwanted commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 unwanted.txt
gymikirengaii@Ikirengas-iMac Git_repo % git reset --hard HEAD~1
HEAD is now at 787239a Create Third file and Create fourth File

```

### 7. Reordering Commits:

```
gymikirengaii@Ikirengas-iMac Git_repo % git log
commit 787239a13ad085277ee2513dea777bb3f89ca0f8 (HEAD -> main, origin/main, origin/HEAD)
Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
Date:   Mon Mar 3 19:19:54 2025 +0200

    Create Third file and Create fourth File

    Create fourth file

commit 80e87a08f531aa8978b9fb8bad2c29208dcaf367
Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
Date:   Mon Mar 3 17:13:41 2025 +0200

    chore: Create initial file

    chore: Create second file

commit 19b4da94db7821b41eb58276ac94e37c9473512d
Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
Date:   Mon Mar 3 17:02:22 2025 +0200

    Initial commit
gymikirengaii@Ikirengas-iMac Git_repo % git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.
gymikirengaii@Ikirengas-iMac Git_repo % git push origin HEAD --force
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (8/8), 1.35 KiB | 1.35 MiB/s, done.
Total 8 (delta 1), reused 5 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To <https://github.com/Ndizihiwe99/Git_repo.git>
 + 85e04bc...d77f34e HEAD -> main (forced update)
gymikirengaii@Ikirengas-iMac Git_repo % git log
commit d77f34e02ae12ede19dfe1b8d5619219ca4fb9fc (HEAD -> main, origin/main, origin/HEAD)
Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
Date:   Mon Mar 3 17:13:41 2025 +0200

    chore: Create initial file

    chore: Create second file

commit 0f2c433a9cb7ad7b8441a5825866f3a83c5eeda9
Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
Date:   Mon Mar 3 19:19:54 2025 +0200

    Create Third file and Create fourth File

    Create fourth file

commit 19b4da94db7821b41eb58276ac94e37c9473512d
Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
Date:   Mon Mar 3 17:02:22 2025 +0200

    Initial commit

```

### 8. Cherry-Picking Commits:

```
gymikirengaii@Ikirengas-iMac Git_repo % git checkout -b ft/branch
Switched to a new branch 'ft/branch'
gymikirengaii@Ikirengas-iMac Git_repo % touch test5.md
gymikirengaii@Ikirengas-iMac Git_repo % git add test5.md
gymikirengaii@Ikirengas-iMac Git_repo % git add .
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "Implemented test 5"
[ft/branch 63faf3e] Implemented test 5
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md
gymikirengaii@Ikirengas-iMac Git_repo % git push origin ft/branch
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (10/10), 1.53 KiB | 1.53 MiB/s, done.
Total 10 (delta 2), reused 4 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), done.
remote:
remote: Create a pull request for 'ft/branch' on GitHub by visiting:
remote:      <https://github.com/Ndizihiwe99/Git_repo/pull/new/ft/branch>
remote:
To <https://github.com/Ndizihiwe99/Git_repo.git>
 * [new branch]      ft/branch -> ft/branch
gymikirengaii@Ikirengas-iMac Git_repo % git cherry-pick --no-commit 63faf3efd2a2d92a4c8fa8fc4d854e600327fbe6
gymikirengaii@Ikirengas-iMac Git_repo % git add .
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "pickked cherry"
[main aed443e] pickked cherry
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md
gymikirengaii@Ikirengas-iMac Git_repo % git push origin HEAD --force
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 234 bytes | 234.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To <https://github.com/Ndizihiwe99/Git_repo.git>
 + 3d62fef...aed443e HEAD -> main (forced update)
gymikirengaii@Ikirengas-iMac Git_repo %

```

### 9. Visualizing Commit History (Bonus):

```
gymikirengaii@Ikirengas-iMac Git_repo % git log --graph
* commit aed443ec81847f91ad25974f082bac5022f5abbb (HEAD -> main, origin/main, origin/HEAD)
| Author: Ndizihiwe99 <eugenekjyn@gmail.com>
| Date:   Tue Mar 4 13:38:48 2025 +0200
|
|     pickked cherry
|
* commit d77f34e02ae12ede19dfe1b8d5619219ca4fb9fc
| Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
| Date:   Mon Mar 3 17:13:41 2025 +0200
|
|     chore: Create initial file
|
|     chore: Create second file
|
* commit 0f2c433a9cb7ad7b8441a5825866f3a83c5eeda9
| Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
| Date:   Mon Mar 3 19:19:54 2025 +0200
|
|     Create Third file and Create fourth File
|
|     Create fourth file
|
* commit 19b4da94db7821b41eb58276ac94e37c9473512d
  Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
  Date:   Mon Mar 3 17:02:22 2025 +0200

      Initial commit
gymikirengaii@Ikirengas-iMac Git_repo %

```

### 10. Understanding Reflogs (Bonus):

```
gymikirengaii@Ikirengas-iMac Git_repo % git reflog
aed443e (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: commit: pickked cherry
d77f34e HEAD@{1}: checkout: moving from ft/branch to main
63faf3e (origin/ft/branch, ft/branch) HEAD@{2}: commit: Implemented test 5
d77f34e HEAD@{3}: checkout: moving from main to ft/branch
d77f34e HEAD@{4}: rebase (finish): returning to refs/heads/main
d77f34e HEAD@{5}: rebase (pick): chore: Create initial file
0f2c433 HEAD@{6}: rebase (pick): Create Third file and Create fourth File
19b4da9 HEAD@{7}: rebase (start): checkout HEAD~2
787239a HEAD@{8}: reset: moving to HEAD~1
bd45c8a HEAD@{9}: commit: Unwanted commit
787239a HEAD@{10}: rebase (finish): returning to refs/heads/main
787239a HEAD@{11}: rebase (start): checkout HEAD~2
54da149 HEAD@{12}: reset: moving to 54da149
787239a HEAD@{13}: reset: moving to HEAD~
54da149 HEAD@{14}: reset: moving to 54da149
54da149 HEAD@{15}: rebase (finish): returning to refs/heads/main
54da149 HEAD@{16}: rebase (start): checkout HEAD~2
54da149 HEAD@{17}: clone: from <https://github.com/Ndizihiwe99/Git_repo.git>
gymikirengaii@Ikirengas-iMac Git_repo %

```

# Part 2: Branching Basics

## 1. Feature Branch Creation:

```
gymikirengaii@Ikirengas-iMac Git_repo % git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
gymikirengaii@Ikirengas-iMac Git_repo %

```

## 2. Working on the Feature Branch:
