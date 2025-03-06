
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

## Part 2: Branching Basics


### 1. Feature Branch Creation:
```
gymikirengaii@Ikirengas-iMac Git_repo % git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
gymikirengaii@Ikirengas-iMac Git_repo %

```

### 2. Working on the Feature Branch:
````
gymikirengaii@Ikirengas-iMac Git_repo %  touch feature.txt 
gymikirengaii@Ikirengas-iMac Git_repo % git add feature.txt
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "Implemented core functionality for new feature"
[ft/new-feature 47d1498] Implemented core functionality for new feature
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt
gymikirengaii@Ikirengas-iMac Git_repo % git push origin ft/new-feature
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 481 bytes | 481.00 KiB/s, done.
Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/Ndizihiwe99/Git_repo/pull/new/ft/new-feature
remote: 
To https://github.com/Ndizihiwe99/Git_repo.git
 * [new branch]      ft/new-feature -> ft/new-feature
````

### 3.Switching Back and Making More Changes:
````
gymikirengaii@Ikirengas-iMac Git_repo % git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
gymikirengaii@Ikirengas-iMac Git_repo % touch readme.txt
gymikirengaii@Ikirengas-iMac Git_repo % git add readme.txt
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "Updated project readme"
[main c74c56d] Updated project readme
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 readme.txt
gymikirengaii@Ikirengas-iMac Git_repo % git push origin HEAD --force                                 
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 253 bytes | 253.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Ndizihiwe99/Git_repo.git
 + 328ffb2...c74c56d HEAD -> main (forced update)
gymikirengaii@Ikirengas-iMac Git_repo % 
````

### 5. Branch Deletion:
````
gymikirengaii@Ikirengas-iMac Git_repo % git fetch origin
remote: Enumerating objects: 11, done.
remote: Counting objects: 100% (11/11), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 9 (delta 5), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (9/9), 4.62 KiB | 525.00 KiB/s, done.
From https://github.com/Ndizihiwe99/Git_repo
   c74c56d..007f736  main       -> origin/main
gymikirengaii@Ikirengas-iMac Git_repo % git pull origin main
From https://github.com/Ndizihiwe99/Git_repo
 * branch            main       -> FETCH_HEAD
Updating c74c56d..007f736
Fast-forward
 README.md | 245 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++-
 1 file changed, 244 insertions(+), 1 deletion(-)
gymikirengaii@Ikirengas-iMac Git_repo % git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt
gymikirengaii@Ikirengas-iMac Git_repo % git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 276 bytes | 276.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: This repository moved. Please use the new location:
remote:   https://github.com/Ndizihiwe99/Git_repo-Advanced-Git.git
To https://github.com/Ndizihiwe99/Git_repo.git
   007f736..36753b6  main -> main
gymikirengaii@Ikirengas-iMac Git_repo % git branch -d ft/new-feature
Deleted branch ft/new-feature (was 47d1498).
gymikirengaii@Ikirengas-iMac Git_repo % 
````
### 6. Creating a Branch from a Commit:
````
gymikirengaii@Ikirengas-iMac Git_repo % git log --oneline --graph
*   36753b6 (HEAD -> main, origin/main, origin/HEAD) Merge with ft/new feature
|\  
| * 47d1498 (origin/ft/new-feature) Implemented core functionality for new feature
* | 007f736 Update README.md
* | b6fbe38 Update README.md
* | c98e219 Update README.md
* | c74c56d Updated project readme
|/  
* aed443e pickked cherry
* d77f34e chore: Create initial file
* 0f2c433 Create Third file and Create fourth File
* 19b4da9 Initial commit
gymikirengaii@Ikirengas-iMac Git_repo % git checkout -b ft/new-branch-from-commit 36753b6
Switched to a new branch 'ft/new-branch-from-commit'
gymikirengaii@Ikirengas-iMac Git_repo % git log --oneline --graph                        
*   36753b6 (HEAD -> ft/new-branch-from-commit, origin/main, origin/HEAD, main) Merge with ft/new feature
|\  
| * 47d1498 (origin/ft/new-feature) Implemented core functionality for new feature
* | 007f736 Update README.md
* | b6fbe38 Update README.md
* | c98e219 Update README.md
* | c74c56d Updated project readme
|/  
* aed443e pickked cherry
* d77f34e chore: Create initial file
* 0f2c433 Create Third file and Create fourth File
* 19b4da9 Initial commit
gymikirengaii@Ikirengas-iMac Git_repo % 
````

### 7.
````
gymikirengaii@Ikirengas-iMac Git_repo % git log
commit 6b2fb60236c11ee9fa800feeb41ca08edc59a7fc (HEAD -> ft/new-branch-from-commit, origin/main, origin/HEAD, main)
Author: Eugene Ndizihiwe <eugenekjyn@gmail.com>
Date:   Thu Mar 6 09:58:12 2025 +0200
````


## Part 3: Advanced Workflows

### 1. Stashing Changes:
````
gymikirengaii@Ikirengas-iMac Git_repo % touch stashFile.md
gymikirengaii@Ikirengas-iMac Git_repo % git add stashFile.md
gymikirengaii@Ikirengas-iMac Git_repo % git stash
Saved working directory and index state WIP on main: 4993f49 Update README.md
````

### 2. Retrieving Stashed Changes:
````
gymikirengaii@Ikirengas-iMac Git_repo % git stash pop
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
(use "git restore --staged <file>..." to unstage)
new file:   [stashFile.md](http://stashfile.md/)

Dropped refs/stash@{0} (90f20b315b74b1a5925fdec4e7671b3a44394333)
````

### 3. Branch Merging Conflicts (Continued):
````
gymikirengaii@Ikirengas-iMac Git_repo % git checkout ft/branch
M test1.md
Switched to branch 'ft/branch'
gymikirengaii@Ikirengas-iMac Git_repo % git add .
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "similating merge confict"
[ft/branch bcb1f09] similating merge confict
1 file changed, 1 insertion(+)
gymikirengaii@Ikirengas-iMac Git_repo % git push --set-upstream origin ft/branch
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 280 bytes | 280.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: This repository moved. Please use the new location:
remote:   https://github.com/Ndizihiwe99/Git_repo-Advanced-Git.git
To https://github.com/Ndizihiwe99/Git_repo.git
63faf3e..bcb1f09  ft/branch -> ft/branch
branch 'ft/branch' set up to track 'origin/ft/branch'.
gymikirengaii@Ikirengas-iMac Git_repo % git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
gymikirengaii@Ikirengas-iMac Git_repo % git add .
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "want to cause merge conflict"
[main 3353d9d] want to cause merge conflict
1 file changed, 1 insertion(+)
gymikirengaii@Ikirengas-iMac Git_repo % git push -f
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 500 bytes | 500.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote: This repository moved. Please use the new location:
remote:   https://github.com/Ndizihiwe99/Git_repo-Advanced-Git.git
To https://github.com/Ndizihiwe99/Git_repo.git

- 302cfb4...3353d9d main -> main (forced update)
gymikirengaii@Ikirengas-iMac Git_repo % git merge ft/branch
Auto-merging [test1.md](http://test1.md/)
CONFLICT (content): Merge conflict in [test1.md](http://test1.md/)
Automatic merge failed; fix conflicts and then commit the result.
gymikirengaii@Ikirengas-iMac Git_repo % git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff tortoisemerge emerge vimdiff nvimdiff
Merging:
[test1.md](http://test1.md/)

Normal merge conflict for '[test1.md](http://test1.md/)':
{local}: modified file
{remote}: modified file
````

### 4. Resolving Merge Conflicts with a Merge Tool:
````
- gymikirengaii@Ikirengas-iMac Git_repo % git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff tortoisemerge emerge vimdiff nvimdiff
Merging:
[test1.md](http://test1.md/)

Normal merge conflict for '[test1.md](http://test1.md/)':
{local}: modified file
{remote}: modified file
Hit return to start merge resolution tool (opendiff): git mergetool --tool -help

xcode-select: error: tool 'opendiff' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance
[test1.md](http://test1.md/) seems unchanged.
Was the merge successful [y/n]? n
merge of [test1.md](http://test1.md/) failed
gymikirengaii@Ikirengas-iMac Git_repo % git merge ft/branch
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
gymikirengaii@Ikirengas-iMac Git_repo % git add .
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "resolved conflict"
[main 5bd3cb8] resolved conflict
gymikirengaii@Ikirengas-iMac Git_repo % git push -f
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 223 bytes | 223.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
remote: This repository moved. Please use the new location:
remote:   https://github.com/Ndizihiwe99/Git_repo-Advanced-Git.git
To https://github.com/Ndizihiwe99/Git_repo.git
3353d9d..5bd3cb8  main -> main
gymikirengaii@Ikirengas-iMac Git_repo % git merge main
Updating bcb1f09..5bd3cb8
Fast-forward
README.md    | 315 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++-
feature.txt  |   0
readme.txt   |   0
stashFile.md |   0
test1.md     |   2 +-
5 files changed, 315 insertions(+), 2 deletions(-)
create mode 100644 feature.txt
create mode 100644 readme.txt
create mode 100644 stashFile.md
````

### 5. Understanding Detached HEAD State:
````
gymikirengaii@Ikirengas-iMac Git_repo % git checkout main
Already on 'main'
Your branch is up to date with 'origin/main'.
gymikirengaii@Ikirengas-iMac Git_repo % 
````

### 6. Ignoring Files/Directories:
````
gymikirengaii@Ikirengas-iMac Git_repo % touch .gitignore
gymikirengaii@Ikirengas-iMac Git_repo % git rm --cached test2.md
fatal: pathspec 'test2.md' did not match any files
gymikirengaii@Ikirengas-iMac Git_repo % git add .gitignore      
gymikirengaii@Ikirengas-iMac Git_repo % git commit -m "stop tracking test2.md"
[main ae9be67] stop tracking test2.md
 2 files changed, 2 insertions(+)
 create mode 100644 .gitignore
 delete mode 100644 test2.md
gymikirengaii@Ikirengas-iMac Git_repo % git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 317 bytes | 317.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: This repository moved. Please use the new location:
remote:   https://github.com/Ndizihiwe99/Git_repo-Advanced-Git.git
To https://github.com/Ndizihiwe99/Git_repo.git
   5bd3cb8..ae9be67  main -> main
gymikirengaii@Ikirengas-iMac Git_repo % git ls-files --others --exclude-standard
test2.md
````

### 7. Working with Tags:
````
gymikirengaii@Ikirengas-iMac Git_repo % git tag v1.0
gymikirengaii@Ikirengas-iMac Git_repo % git push origin v1.0
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote: This repository moved. Please use the new location:
remote:   https://github.com/Ndizihiwe99/Git_repo-Advanced-Git.git
To https://github.com/Ndizihiwe99/Git_repo.git
 * [new tag]         v1.0 -> v1.0
gymikirengaii@Ikirengas-iMac Git_repo % git tag
v1.0
gymikirengaii@Ikirengas-iMac Git_repo % git tag v1.0
fatal: tag 'v1.0' already exists
````

### 8. Listing and Deleting Tags:
````
gymikirengaii@Ikirengas-iMac Git_repo % git tag
v1.0
v1.2
gymikirengaii@Ikirengas-iMac Git_repo % git tag -d v1.2 
Deleted tag 'v1.2' (was ae9be67)
````

### 9. Pushing Local Work to Remote Repositories:
````
gymikirengaii@Ikirengas-iMac Git_repo % git push origin v1.0
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote: This repository moved. Please use the new location:
remote:   https://github.com/Ndizihiwe99/Git_repo-Advanced-Git.git
To https://github.com/Ndizihiwe99/Git_repo.git
 * [new tag]         v1.0 -> v1.0
````

### 10. Pulling Changes from Remote Repositories:
````
gymikirengaii@Ikirengas-iMac Git_repo % git pull origin main
From https://github.com/Ndizihiwe99/Git_repo
 * branch            main       -> FETCH_HEAD
Already up to date.
````

