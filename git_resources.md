https://www.toptal.com/git/tips-and-practices
https://www.atlassian.com/git/tutorials/what-is-version-control

git config --global user.name "David Yako"
git config --global user.email "david@gmail.com"

git config --global core.autocrlf input #mac
git config --global core.autocrlf false #removes lr wanring for the PC 

git config --list #view your settings 
git config --help

q! # exit without saving 
wq # exit and save 
:wq #exit and save as well 

ctrl + x, Y, enter #saving in nano 
ls -A #Shows hidden files and folders 

git clone [url here] ~/Desktop #from the remote web, auto initializes git
git init  #Only do on local host computer :8888

mkdir directory_name #Creates directory
touch file_name.txt #Creates file
nano .gitignore #sees code to ignore files 

git config --global core.autocrlf false #For PC to disable LF warning 

Git log #View commits
git commit --author="Vlad Dracula <vlad@tran.sylvan.ia>"
1. Create folder, file, or make an edit change
git diff #--color-words #see changes before staging
2. git add filename or git add . #staging prep for one or all file/folder changes 
git diff --staged
git status
3. git commit -m "comment goes here" #commits the track change to log
git status
git log --patch cats.txt #Shows log and diff together
4. git push origin master
git remote add origin url #becomes master 

git remote -v #fetches from remote to local 
git push -u origin master #Sends to web 

git log --patch filename.txt
git log -1
git log --oneline #shows as one line per commit 
git log --format=full
shift :q #exit vim

Try git commit #without message
git add . #show for all 

# Revision changes 
1. git diff HEAD or 8a61d07 mars.txt #show the most recent change(s)
git diff HEAD~1 mars.txt
2. git show HEAD~2 mars.txt #view version to roll back
ctrl + shift + c #gitbash copy for PC 
ctrl + v #pastes for gitbash 
3. git checkout HEAD~1 or f22b25e mars.txt # roll back one line
git reset HEAD mars.txt #removes staged files
git checkout -f master mars.txt #Checks out one previous commit on Github

unset SSH_ASKPASS #asks for password 
#For Proxys
git config --global http.proxy http://user:password@proxy.url
git config --global https.proxy http://user:password@proxy.url

# Merge conflicts between branches


git checkout feature 
git rebase -i master

git checkout feature
git merge master 
git merge master feature 

git revert 
git checkout 

git push --force

git merge-base feature master 

git stash # code available for later
git stash list # see the changes 
git stash apply #applies stash 
git stash apply stash@{1}
git checkout . # reset all uncomitted code
git stash branch 'debugging-branch' # saves stashes in new branch 
git stash drop stash@{2} #drops one stash at a time 
git stash clear # removes all stashes 

git reset --soft HEAD~1 # soft reset against messy code, but still exists so you can fix and re-commit 
git reset --hard HEAD~1 #permanently erases previous commit

git bisect start #launches git bisect utility 
git bisect bad [commitID] #indicate where a problem exists

git checkout [commitID] # to examine when in git bisect where the problem no longer occured

git bisect good [commitID] #git searches for where issue occured and resolves 
git bisect bad [no commit ID needed]  # if still bad 

git bisect good #once it's good 
git show #reveal the commit and where issue occured 

git bisect reset #reset branch to normal working state after 

git rebase -i HEAD~2 # be presented with last 3 commits --root # for local
pick [commitID] # a screen will appear and you can change all before pick to say squash to merge them
squash [commitID] # squash specific id into the pick 
git push 
git push --force #forces the push
Git rebase --abort #cancels the rebase 

git checkout #to explore changes to consider to commits 

git add -A  #git knows to remove it 
git commit --amend -v #to edit commit message 
git rebase --onto HEAD [commitID] master 


git rebase --continue 
git rebase --skip 
