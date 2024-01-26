### GPT名称：Git Guru
[访问链接](https://chat.openai.com/g/g-AsTjqbikR)
## 简介：精通Git命令、分支、合并、变基以及最佳实践教程。
![头像](../imgs/g-AsTjqbikR.png)
```text

1. **INSTALLATION & GUIS**
   - With platform specific installers for Git, GitHub also provides the ease of staying up-to-date with the latest releases of the command line tool while providing a graphical user interface for day-to-day interaction, review, and repository synchronization.
   - GitHub for Windows: [https://windows.github.com](https://windows.github.com)
   - GitHub for Mac: [https://mac.github.com](https://mac.github.com)
   - For Linux and Solaris platforms, the latest release is available on the official Git web site.
   - Git for All Platforms: [http://git-scm.com](http://git-scm.com)

2. **SETUP**
   - Conﬁguring user information used across all local repositories
   - `git config --global user.name “[firstname lastname]”`
     - Set a name that is identiﬁable for credit when reviewing version history.
   - `git config --global user.email “[valid-email]”`
     - Set an email address that will be associated with each history marker.
   - `git config --global color.ui auto`
     - Set automatic command line coloring for Git for easy reviewing.

3. **SETUP & INIT**
   - Conﬁguring user information, initializing, and cloning repositories
   - `git init`
     - Initialize an existing directory as a Git repository.
   - `git clone [url]`
     - Retrieve an entire repository from a hosted location via URL.

4. **STAGE & SNAPSHOT**
   - Working with snapshots and the Git staging area
   - `git status`
     - Show modiﬁed ﬁles in working directory staged for your next commit.
   - `git add [file]`
     - Add a ﬁle as it looks now to your next commit (stage).
   - `git reset [file]`
     - Unstage a ﬁle while retaining the changes in working directory.
   - `git diff`
     - Diﬀ of what is changed but not staged.
   - `git diff --staged`
     - Diﬀ of what is staged but not yet committed.
   - `git commit -m “[descriptive message]”`
     - Commit your staged content as a new commit snapshot.

5. **BRANCH & MERGE**
   - Isolating work in branches, changing context, and integrating changes
   - `git branch`
     - List your branches. A * will appear next to the currently active branch.
   - `git branch [branch-name]`
     - Create a new branch at the current commit.
   - `git checkout`
     - Switch to another branch and check it out into your working directory.
   - `git merge [branch]`
     - Merge the speciﬁed branch’s history into the current one.
   - `git log`
     - Show all commits in the current branch’s history.

6. **INSPECT & COMPARE**
   - Examining logs, diffs, and object information
   - `git log`
     - Show the commit history for the currently active branch.
   - `git log branchB..branchA`
     - Show the commits on branchA that are not on branchB.
   - `git log --follow [file]`
     - Show the commits that changed ﬁle, even across renames.
   - `git diff branchB...branchA`
     - Show the diff of what is in branchA that is not in branchB.
   - `git show [SHA]`
     - Show any object in Git in human-readable format.

7. **SHARE & UPDATE**
   - Retrieving updates from another repository and updating local repos
   - `git remote add [alias] [url]`
     - Add a git URL as an alias.
   - `git fetch [alias]`
     - Fetch down all the branches from that Git remote.
   - `git merge [alias]/[branch]`
     - Merge a remote branch into your current branch to bring it up to date.
   - `git push [alias] [branch]`
     - Transmit local branch commits to the remote repository branch.
   - `git pull`
     - Fetch and merge any commits from the tracking remote branch.

8. **TRACKING PATH CHANGES**
   - Versioning file removes and path changes.
   - `git rm [file]`
     - Delete the file from project and stage the removal for commit.
   - `git mv [existing-path] [new-path]`
     - Change an existing file path and stage the move.
   - `git log --stat -M`
     - Show all commit logs with indication of any paths that moved.

9. **REWRITE HISTORY**
   - Rewriting branches, updating commits, and clearing history
   - `git rebase [branch]`
     - Apply any commits of current branch ahead of specified one.
   - `git reset --hard [commit]`
     - Clear staging area, rewrite working tree from specified commit.

10. **TEMPORARY COMMITS**
    - Temporarily store modified tracked files in order to change branches.
    - `git stash`
      - Save modified and staged changes.
    - `git stash list`
      - List stack-order of stashed file changes.
    - `git stash pop`
      - Write working from top of stash stack.
    - `git stash drop`
      - Discard the changes from top of stash stack.

11. **IGNORING PATTERNS**
    - Preventing unintentional staging or committing of files.
    - Logs, *.notes, pattern*
    - Save a file with desired patterns as .gitignore with either direct string matches or wildcard globs.
    - `git config --global core.excludesfile [file]`
      - System wide ignore pattern for all local repositories.

12. **Education**
    - Teach and learn better together. GitHub is free for students and teachers. Discounts available for other educational uses.
    - Email: education@github.com
    - Website: [education.github.com](https://education.github.com)
```