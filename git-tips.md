## GIT TIPS

#### Add
    git add .
    git add filename
    git add -i # interactive mode
    git add -p <filename_to_interactively_stage_patches_from>

#### Branch
    git branch # show local branches
    git branch -r # show remote branches (after fetch)
    git branch -d <localbranch> # delete
    git branch -D <local_branch_with_uncommitted_items> # force delete
    git branch --merged # local branches merged into current branch
    git branch --no-merged # local branches not merged into current branch
    git branch -r --merged # remote branches merged
    git branch -r --no-merged # remote branches not merged
    git branch --merged HEAD
    git branch --merged <branch_name>
    git branch --merged origin/master
    git branch --merged <commit_#>

#### Commit
    git commit -m "log message" # if already staged
    git commit -am "log message" # stage all and commit

#### Delete
    # Also see Branch
    git push origin --delete <remote_branch> # delete remote branch
    git push origin -d <remote_branch>

#### Diff
    git diff # what's in working dir vs HEAD
    git diff --cached # what's staged vs HEAD
    

#### Log
    git log
    git log --abbrev-commit --pretty=oneline
    git log origin/master
    git log <branch_name>

#### Misc
    git checkout -b <new_branch_name>
    git fetch
    git gc # manually clean up repo vice wait for automated sweep
    git remote prune origin --dry-run # del tracking branch when remote branch deleted by someone else
    git reset --hard origin/master
    git status

#### Push
-u = set the local up to track the origin

    git push -u origin master
    git push -u origin <branch_name>
    git push --force # warning: destructive!

#### Tag
    git tag -ln # list tags
    git tag -a "v0.1" -m "Version 0.1" # tag HEAD
    git tag -a "v0.1" -m "Version 0.1" <commit_#> # tag specific commit
    git push origin --tags
