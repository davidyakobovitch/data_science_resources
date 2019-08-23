<font size="4em"><strong>Git Version Control</strong></font>

###### Git Commands
```bash
When a # is used, this indicates a comment
When a <> is used, this indicates the location for a file, tag, hash, etc.
```

###### Configuration Settings 
```bash
git config --global user.name "David Yakobovitch" # Set a name for commits
git config --global user.email "david@gmail.com" # Set an e-mail for commits
git config --global core.askpass # If wrong password typed, remind Github/Bitbucket/Gitlab to ask for password
git config --global core.autocrlf input # Disable CR LF message
git config --global core.autocrlf false # Disable CR LF message
git config --global core.editor "code" # Set your preferred text editor with Git
git config --list # View configuration settings
git config --help # View help for configuration options
git config --global rerere.enabled true # Avoid Repeated Merge conflicts
git config --global http.proxy http://user:password@proxy.url # Configure proxy credentials
git config --global https.proxy http://user:password@proxy.url
```

###### Clone a repository from Github
```bash
git clone [_url_here] [directory_name_here] [local_file_path_here]
git clone <dir> <new_dir_name> # Creates a clone of directory as new repository locally
```

###### Pull a Remote Repository
```bash
git pull # Equivalent to git fetch, and then git merge origin/master 
```

###### Remote repositories
```bash
git remote -v # View the remote repository location
git remote # View the remote repository name
git remote show <repo_name> # Shows info about the remote repository
git remote add shared <repo_location> # Adds the repo as a remote to original repo
git remote add origin url #becomes master 
```

###### Initalize a local git on host machine
```bash
git init [directory_name]
git init # inside the directory
```

###### Create a new directory or file
```bash
mkdir [directory_name] #create directories
touch [file_name.extension] #create empty files
echo "text goes here" > file.txt #creates new file with text values
```

###### Stage changes to the active directory
```bash
git add . # all changes to be logged
git add [file.txt] # logs a file change
git add [file-1.text] [file-2.txt] # logs file changes for specific files
```

###### Commit changes to the git log
```bash
git commit -m "message goes here"
git commit --message "message goes here"
git commit --author="Vlad Dracula <vlad@tran.sylvan.ia>" # chan
git commit --amend -m "comment" #Amends most recent commit for small update, shorter than a reset w/ commit
git commit -a -m 'added new benchmarks' # Adds all changes and commits in one line
git commit --author="David Yakobovitch <david@gmail.com>" # Change author for a specific commit message
git commit --amend                  # start $EDITOR to edit/amend the message
```

###### Status - show changes to the version controlled files
```bash
git status
git status --short # See abbreviated changes
git status -s # See abbreviated changes
```

###### Show changes before and after staging as colored-words
```bash
git diff # Shows changed before git add
git diff --staged # Shows changed after git add before git commit
git diff HEAD <hash> <file_name> # Show the most recent changes for file on a Hash commit
git diff HEAD~1 <file_name> # Shows changes to file one previous version
git diff master..<branch_name> #Display differences between branches
git diff format-patch master..<branch_name> # Generates a file with patch for each commit reachable in the branch but not from the master
```

###### View completed commits
```bash
git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
git log --pretty=oneline --max-count=2
git log --pretty=oneline --since='15 minutes ago'
git log --pretty=oneline --until='15 minutes ago'
git log --pretty=oneline --all
git log --all --pretty=format:'%h %cd %s (%an)' --since='7 days ago'
git log
git log --patch cats.txt # Shows log and diff together
git log -2 # Shows 2 most recent commits
```

###### .gitignore files
```bash
[text_editor_name] .gitignore
nano .gitgnore
*.a # Do ignore all files with this extension
!lib.a # Do not ignore this file
doc/*.txt # Ignore only files in doc directory ending in extension
doc/**/*.pdf # Ignore all files in doc directory and sub-directories ending in extension 
build/ # Ignore all files in directory named build
/heart # Ignore the heart file in current directory
echo filename >> .gitingore # add it to .gitignore to avoid re-adding it
```

###### Tags: A replacement for Hash strings
```bash
git tag -l # View the tag history as a list
git tag v1 # Adds a tag to a commit
git tag <tag_name> <hash> # Adds a tag to a commit named with its hash 
git tag -d tagname # Deletes the tag name
```

###### Checkout: Recover previous verisons
```bash
git checkout v1 # Checkout the branch to a specific commit with tag
git checkout v2~1 # Checkouts 1 previous version with tag
git checkout v2^1 # Checkouts 1 previous version with tag
git checkout <file_name> #Checkouts a specific filename
git checkout . # Reset all uncomitted code
git checkout HEAD~1 # Roll back one version
git checkout <hash> <file_name> # Roll back one version for a file
git checkout -f master <file_name> # Checks out one previous commit for file from Github/Bitbucket/Gitlab
git checkout master
```

###### Remove a file
```bash
git rm <filename> # Stages or adds the file for removal before commit
```

###### Reset to undo changes
```bash
git reset HEAD <filename> # Undoes changes to the file from recent commit
git reset --hard <tag or hash> # Undoes commit back to the previous version
git fetch origin # Drops all your local changes and fetches latest history from server 
git reset HEAD <file_name> # Removes staged files
git reset HEAD~2        # Undoes last two commits, keep changes
git reset --hard HEAD~2 # Undoes last two commits, discard changes  
git reset <file_name>      # Removes file; same operation as git remove --cached <file_name>
git reset --soft HEAD~1 # Soft reset against messy code, but still exists so you can fix and re-commit 
git reset --hard HEAD~1 # Permanently erases previous commit
```

###### Revert commits to previous states
```bash
git revert HEAD #Reverts changes after committing if accidently committed
git revert c761f5c              # reverts the commit with the specified id
git revert HEAD^                # reverts the second to last commit
git revert develop~4..develop~2 # reverts a whole range of commits
git revert -n HEAD # undo the last commit, but don't create a revert commit 
```

###### History: View all commits
```bash
# First, be sure to set in ~/.gitconfig an [alias] for hist
# [alias]
# hist = log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
git hist master --all # Show all commit history
git hist --all # Show all history, even when a hard reset is performed, as all history is preserved
git hist --stat # Shows changes per each file as well
# Note: HEAD is the currently checked out commit.
```

###### Display the most recent commit
```bash
git show # Displays the most recent commit on the HEAD
git show HEAD~2 mars.txt # View version to roll back
git show HEAD^ or git show HEAD^1 or git show HEAD~ # View the parent of the HEAD commit
git show HEAD^^ # View the grandparent or second parent of the HEAD commit
git show <tag or hash>:<file_name> # View old version of the file
```

###### Rev-list: Display git quantity difference
```bash
git rev-list master..<your_branch> | wc -l # View how many commits ahead your branch is over the master/origin
```

###### Display the commit in a pretty-print format
```bash
git cat-file -p <commit-ID> #can be run on the tree (points to blobs), blob (sub-directory of files) or commit (points to tree) 
```

###### Re-load shell with updates to profile or config
```bash
source ~./profile
source ~/.gitconfig 
```

###### Dump files to your terminal
```bash
cat .git/objects/ce/<commit> | inflate | wc -c # Display wordcoutn of an object (requirs ruby installation)
cat .git/objects/ce/<commit> | inflate | hexdump -C # Explore hex characters
```

###### Gitk or Visual interactive (Personally recommend Fork software for Mac/Windows)
```bash
gitk # Visual interactive of all commits in a git repository
```

###### Push updates to Online repository
```bash
git push origin master # Pushes the updates to the master branch
git push -u origin master
git push --force # forces a push, could have issues with conflicts
git push shared master # Push changes to a remote shared repository 
```

###### Merging Branches
```bash
git merge feature # The feature branch merges into the master branch 
git merge master feature 
git merge-base feature master 
git merge origin/master # Can locally merge changes after a git fetch if desired
```

###### Branching
```bash
git branch <branch_name> # Creates a new branch
git checkout -b <branch_name> # Creates a new branch and switches to the branch 
git branch # View all local branches
git branch -a # View all branches
git branch -d <branch_name> # Deletes a branch 
git branch --track <branch_name> origin/<branch_name> # Add a local branch that tracks a remote branch
git branch -r # Examine branches being tracked from remote repositories
```

###### Fetching Remote Updates
```bash
git fetch # Retrieves updates from remote repo but does not merge them
```

###### Bare Repositories
```bash
git clone --bare hello hello.git # Used for sharing commits without files
```

###### Rebase or merge branches together and other commands
```bash
git rebase -i master
git rebase -i HEAD~2 # be presented with last 3 commits --root # for local
git rebase --onto HEAD [commitID] master 
git rebase --continue 
git rebase --skip 
git rebase --interactive 
git rebase --interactive origin branch
git rebase --abort #cancels the rebase 
git stash # code available for later
git stash list # see the changes 
git stash apply #applies stash 
git stash apply stash@{1}
git stash branch 'debugging-branch' # saves stashes in new branch 
git stash drop stash@{2} #drops one stash at a time 
git stash clear # removes all stashes 
git bisect start #launches git bisect utility 
git bisect bad [commitID] #indicate where a problem exists
git bisect good [commitID] #git searches for where issue occured and resolves 
git bisect bad [no commit ID needed]  # if still bad 
git bisect good #once it's good 
git bisect reset #reset branch to normal working state after 
pick [commitID] # a screen will appear and you can change all before pick to say squash to merge them
squash [commitID] # squash specific id into the pick 
git checkout -- Gemfile # reset specified path 
ctrl + shift + c #gitbash copy for PC 
ctrl + v #pastes for gitbash 
unset SSH_ASKPASS #asks for password 
```

###### Gitbash Shortcuts
<li>Ctrl-a		Move to the start of the line.</li>
<li>Ctrl-e		Move to the end of the line.</li>
<li>Ctrl-b		Move back one character.</li>
<li>Alt-b		Move back one word.</li>
<li>Ctrl-f		Move forward one character.</li>
<li>Alt-f		Move forward one word.</li>
<li>Ctrl-] x	Where x is any character, moves the cursor forward to the next occurance of x.</li>
<li>Alt-Ctrl-] x	Where x is any character, moves the cursor backwards to the previous occurance of x.</li>
<li>Ctrl-u		Delete from the cursor to the beginning of the line.</li>
<li>Ctrl-k		Delete from the cursor to the end of the line.</li>
<li>Ctrl-w		Delete from the cursor to the start of the word.</li>
<li>Esc-Del		Delete previous word (may not work, instead try Esc followed by Backspace)</li>
<li>Ctrl-y		Pastes text from the clipboard.</li>
<li>Ctrl-l		Clear the screen leaving the current line at the top of the screen.</li>
<li>Ctrl-x Ctrl-u	Undo the last changes. <li>Ctrl-_ does the same</li>
<li>Alt-r		Undo all changes to the line.</li>
<li>Alt-Ctrl-e	Expand command line.</li>
<li>Ctrl-r		Incremental reverse search of history.</li>
<li>Alt-p		Non-incremental reverse search of history.</li>
<li>!!		Execute last command in history</li>
<li>!abc		Execute last command in history beginning with abc</li>
<li>!abc:p		Print last command in history beginning with abc</li>
<li>!n		Execute nth command in history</li>
<li>!$		Last argument of last command</li>
<li>!^		First argument of last command</li>
<li>^abc^xyz	Replace first occurance of abc with xyz in last command and execute it</li>

###### Aliases for .profile or [alias] for .gitconfig
```
alias gaa='git add .'
alias gc='git commit'
alias ga='git add'
alias gaaa='git add --all'
alias gau='git add --update'
alias gb='git branch'
alias gbd='git branch --delete '
alias gcm='git commit --message'
alias gcf='git commit --fixup'
alias gco='git checkout'
alias gcob='git checkout -b'
alias gcom='git checkout master'
alias gcos='git checkout staging'
alias gcod='git checkout develop'
alias gd='git diff'
alias gda='git diff HEAD'
alias gi='git init'
alias glg='git log --graph --oneline --decorate --all'
alias gld='git log --pretty=format:"%h %ad %s" --date=short --all'
alias gm='git merge --no-ff'
alias gma='git merge --abort'
alias gmc='git merge --continue'
alias gp='git pull'
alias gpr='git pull --rebase'
alias gr='git rebase'
alias gs='git status'
alias gss='git status --short'
alias gst='git stash'
alias gsta='git stash apply'
alias gstd='git stash drop'
alias gstl='git stash list'
alias gstp='git stash pop'
alias gsts='git stash save'
```

###### References 
- [Atlassian Version Control](https://www.atlassian.com/git/tutorials/what-is-version-control)
- [Git Manual Online](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/)
- [Git User Manual](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/user-manual.html)
- [Blog: The Thing About Git](https://tomayko.com/blog/2008/the-thing-about-git)
- [The Simple Git Guide](http://rogerdudler.github.io/git-guide/)
- [Pro Git Book](https://book.git-scm.com/book/en/v2)
- [Github.com Help](https://help.github.com/en)
- [Think Like a Git](http://think-like-a-git.net/)
- [Fork - Merge Visualizer for Windows/Mac](https://fork.dev/windows)
- [Git Immersion](gitimmersion.com)
- [Toptal Best Practices](https://www.toptal.com/git/tips-and-practices)
- [Git Workflows](https://www.toptal.com/git/git-workflows-for-pros-a-good-git-guide)
- [Advanced Git Commands](https://www.toptal.com/git/the-advanced-git-guide)

###### FAQs:
- [Set up Tree on Windows](https://superuser.com/questions/531592/how-do-i-add-the-tree-command-to-git-bash-on-windows)
- [Rename Windows Computer in Git Bash](https://kb.iu.edu/d/ajnx)
- [Customize Gitbash Display Windows](https://alanbarber.com/post/how-to-customize-the-git-for-windows-bash-shell-prompt/)
- [Change Default Git location for Jupyter and Git Bash Windows](http://practicalseries.com/1002-vcs/03-03-install.html)
- [Set Conda Commands from Git bash Windows 10](https://stackoverflow.com/questions/44597662/conda-command-is-not-recognized-on-windows-10?rq=1)
- [Reset HTTPS Proxy Git Bash](https://stackoverflow.com/questions/32268986/git-how-to-remove-proxy/32269086)
- [Change SSH to HTTPS Git](https://help.github.com/en/articles/changing-a-remotes-url)
- [Customize Alias on Mac for Git](https://stackoverflow.com/questions/2553786/how-do-i-alias-commands-in-git)
- [Create Additional Git Aliases](https://jonsuh.com/blog/git-command-line-shortcuts/)
- [Set Aliases Git Bash Windows](http://kurtdowswell.com/software-development/git-bash-aliases/)