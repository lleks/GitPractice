# Hello World repository for Git tutorial

>**Git version**
>
> `git --version`

>**Configure Git**
>
>`git config --global user.name "Alex"`
>
>`git config --global user.email "Alex@gmail.com"`

>**Generating an SSH Key Pair**
>
>`ssh-keygen -t rsa -b 4096 -C "Alex@gmail.com"`
>
>`ssh-keygen`
>
>Note:
>1. Add this SSH key pair to the SSH-Agent
>
>`ssh-add /Users/user/.ssh/id_rsa`
>
>2. Copy the SSH Public Key
>
>`clip < /Users/user/.ssh/id_rsa.pub`
>
>3. Test SSH Connection to GitHub
>
>`ssh -T git@github.com`


>**Creating Git Folder**
>
>`mkdir GitPractice` Create a new directory "GitPractice":
>
>`cd GitPractice` Changes the current working directory

>**Initialize Git**
>
>`git init`

>**Create new file**
>
>`touch index.html`

>**Edit file and save**
>
>`vim index.html`

>**How to exit Vim:**
>
>`:x` or `:wq` 	- save and exit
>
>`:w` 		- save changes
>
>`:q` 		- exit from Vim if nothing was changed
>
>`:q!`		- exit Vim and discard any changes

>**After new file wasa added**
>
>`git status`
>
>`git status --short`
>
>Note: Short status answer flags are:
>
>`??` 	- Untracked files
>
>`A` 	- Files added to stage
>
>`M` 	- Modified files
>
>`D` 	- Deleted files

>**Add file to the Staging Environment**
>
>`git add index.html`

>**Git Add More than One File**
>
>`git add --all`
>
>`git add -A`
>
>`git add *`
>
>`git add .`

>**Adding commits**
>
>`git commit -m "First release of Hello World!"`	(-m means "message")

>**Git Commit without Stage**
>
>`git commit -a -m "Updated index.html with a new line"`

>**Rollback file to previous commit state**
>
>`git restore index.html`
>
>`git restore --staged index.html` 
>
>`git checkout index.html`

>**Changes for the last commit shown**
>
>`git diff`
>
>`git diff --staged`	Changes for staged environment shown

>**Git Commit Log** (to view the history of commits for a repository)
>
>`git log`
>
>`git log -p`

>**Show info about commit**
>
>`git show 0936bcf7c5bbb4fcfe8b4e1a2f29e018b0d7a301`

>**Git Help**
>
>`git command -help`		All the available options for the specific command are shown
>
>`git help --all`		All possible commands are shown
>
>Note:
>
>`SHIFT + G`	 to jump the end of the list
>
>`q`		 to exit the view

>**Create a new branch**
>
>`git branch hello-world-images`		(a new branch called "hello-world-images" was created)
>
>`git checkout -b hello-world-images`	(create, and move to a new branch with the name "hello-world-images")

>Let's confirm that we have created a new branch
>
>`git branch`
>
>`git branch -a`		all local and remote branches shown
>
>`git branch -r`		for remote branches only

>**Moving from the current branch, to the one specified at the end of the command**
>
>`git checkout hello-world-images`

>**Switching Between Branches**
>
>`git checkout master`

>**Merge Branches**
>
>`git checkout master`		we need to change to the master branch
>
>`git merge emergency-fix`	now we merge the current branch (master) with emergency-fix

>**Deleted branch**
>
>`git branch -d emergency-fix`
>
>`git branch -D emergency-fix`		if changes was not merged in any other bunch

>**Move HEAD and current branch to selected commit** (previous commit was not show anymore)
>
>`git reset --hard 0936bcf7c5bbb4fcfe8b4e1a2f29e018b0d7a301` 

>**Push Local Repository to GitHub**
>
>1. Create a Repository on GitHub
>2. Copy the Repository URL
>3. `git remote add origin https://github.com/....`
>4. `git push --set-upstream origin master`		(push our master branch to the origin url)

>**Git Fetch** (gets all the change history of a tracked branch)
>
>`git fetch origin`

>**View existing repositories**
>
>`git remote -v`

>**Push to GitHub**
>
>`git push origin`

>**Clone project from GitHub**
>
>`git clone git@github.com:lleks/GitPractice.git`

>**Add tag on commit** (v1 tag name)
>
>`git tag v1`
>
>`git tag -a v1 -m "new tag"`

>**View all tags**
>
>`git tag`

>**Send branch on GitHub with tag**
>
>`git push origin v1`
>
>`git push --tags` (for all tags)

>**Git GitHub Fork and Pull Request**
>
>1 Fork a Repository (Now we have our own copy of a Repository in our GitHub page)
>
>2 Move back to the original repository, and `Clone` it to local repository in our PC
>
>`git clone https://github.co...`
>
>Navigate to the new directory, and check the `status`:
>
>`cd w3schools-test.gi...`
>
>`git status`
>
>Check the `log` to confirm that we have the full repository data:
>
>`git log` (now we have a full copy of the original repository)
>
>3 Configuring Remotes
>Basically, we have a full copy of a repository, whose `origin` we are not allowed to make changes to.
>
>Let's see how the `remotes` of this Git is set up:
>
>`git remote -v`
>
>We see that `origin` is set up to the original repository, we also want to add our own `fork`.
>
>First, we `rename` the original `origin` `remote`:
>
>`git remote rename origin upstream`
>
>`git remote -v`
>
>Then `clone` our own fork
>
>And add that as `origin`:
>
>`git remote add origin https://github.com/lle...`
>
>`git remote -v`
>
>Note: According to Git naming conventions, it is recommended to name your own repository origin, and the one you forked for upstream
>
>Now we have 2 remotes:
> - `origin` - our own `fork`, where we have read and write access
> - `upstream` - the original, where we have read-only access
>
>4 Make some changes to the code in our local Git
>
>5 Now we `push` them to our GitHub `fork`:
>
>`commit` the changes:
>
>`git push origin`
>
>6 Go to our forked GitHub project page, the repository has a new commit. We can send a Pull Request to the original repository.


