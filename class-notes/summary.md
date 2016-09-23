## GitHub for Developers

These are for use during webinars of GitHub for Developers. They are organized by module, and should be sent during breaks in Gitter or chat.

### Getting Ready for Class
- Make sure you have [Git insalled](https://git-scm.com/) on your computer and a [GitHub account](https://github.com/).

### Getting Started
**Quick review of what we've covered so far:**
- Repository for Class: https://github.com/githubteacher/sep-19-developers
- Tour of Repository: 
  - Code View:  Files belonging to the project
  - README.md: Description of the Repository 
  - Issues: A place to have conversations and collaborate
  - Pull requests: A place to collaborate while introducing changes to your project
- Look for the issue that will add you as a collaborator in the issues tab.
- Practice making an issue in the issues tab of the class repository.
  - For today's activity, be sure to include your username in the title, like "YourUserName Hometown"
  - In the body of the issue, we added the steps we'll take for the workflow. 
  - Our goal later will be to add a document with information about your hometown, like good restaurants or things to do. 
  - You can include [markdown](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf) syntax here.

**Getting access to the collaborator script:**
The collaborator script is open-source! You can access it [here](https://github.com/github/training-utils). Our [training kit](https://github.com/github/training-kit) is also open-source. We invite you to use these and welcome contributions to both these repos!

### GitHub Flow
**You can find that visual of the GitHub flow at this link:** https://guides.github.com/introduction/flow/

### Branching with Git
**Review of branches**
- When you create a branch, you are essentially creating an identical copy of the project at that point in time that is completely separate from the master branch.
- Create a branch on GitHub.com in the class repository
  - Click the 'branch' dropdown 
  - Enter a branchname name 'firstname-lastname-hometown'


### Local Git Configs
**Review of configurations:**
- We determined our git version by running `git --version`... version 1.9+ is recommended
- If you need to, you can install it [here](https://git-scm.com/)
- If you don't already have GitHub Desktop, you can install it [here](https://desktop.github.com/)
- Clone the repository by running `git clone <URL>` (Make sure you are in the directory where you want the repository to be when you run this command)
- Set up your Git configurations by running these commands:
  - `git config --global user.name "your name"`
  - `git config --global user.email <youremail@email.com>`
  - `git config --global core.editor <editor>` (For more help associating your text editor with Git, read [this GitHub Help article](https://help.github.com/articles/associating-text-editors-with-git/).
  - `git config --global push.default simple`
  - Windows ONLY: `git config --global core.autocrlf true`
  - Mac and Linux ONLY: `git config --global core.autocrlf input`
- Check your configurations by running `git config --list`

### Working Locally
**Review of working locally**
- Working on our new branch, we created a new file.
- List the files in your current directory by running `ls -la`
- We learned about 'working', 'staging', and 'history' and how commits fit into those areas using [this resource](https://services.github.com/kit/modules/CONT-CLI-04_Two_Stage_Commit.html).
- See your working/staged area  `git status`. This command is :heart:! 
 
   1. Change your file from 'working' to 'staging' by running `git add <file-name>`
   2. Change your file from 'staging' to 'history' by running `git commit`
   3. Text editor opens: Write a 'commit message' tells a story of the changes you just made in 50 characters or less.

- Create a new file and repeat steps 1 - 3 for the two stage commit. This way, we'll have two commits to work with.
- Here are some shortcuts to know about in the future:
  - To automatically stage all files that have been changed, run `git add -A`. Note: This will only work for files that are already being tracked, not brand new files.
  - Avoid the text editor in the commit by running `git commit -m "commit message"`

### Collaborating on Code
**Review of moving from Git to GitHub**
- We talked about _remote_, and how we can see details about it by running `git remote`, `git remote -v`, and `git remote show origin`
- 'Push' our changes on the current branch to GitHub.com by running `git push -u origin <branch-name>`
- If you forget the `-u` tag, set a 'upstream branch' relationship between our local branch and the GitHub.com remote branch by running `git branch --set-upstream-to=origin/<remote-branch-name>`
  - This means we only have to run `git push` and `git pull` in the future
    - git pull is the combination of git fetch and git merge
- `git branch` and `git branch -a` will help you see what is going on with your local and remote branches
- On GitHub.com, open a pull request in our [class repository](https://github.com/githubteacher/github-for-developers-2016-04) by clicking the green "New pull request" button.
  - Make sure your pull request says `base: master` and `compare: <your-new-branch>`
  - Give it a good title and message about the changes you introduced. Bonus points for using [markdown](https://guides.github.com/features/mastering-markdown/) and emojis!
  - You can add labels and assignees to pull requests like we did with Issues.
- Using @mention is important - you can mention people or teams to give them a notification to see your pull request to start collaboration.

**Notifications**
- Notifications are an important part of GitHub. You can customize these several ways.
  - For GitHub in general, [Settings/notificatons](https://github.com/settings/notifications)
  - For repositories, at the top of a repository page on GitHub.com by clicking "Watch"
  - For individual issues and pull requests by clicking "unsubscribe" on the right hand side of the webpage
- On the pull request page, we talked about the different tabs for 'conversation', 'commits', and 'files changed'.
  - 'Conversation' is where you and your colleagues can collaborate on your changes. This view includes comments as well as notes of when changes happen.
  - 'Commits' shows a history of what commits were added - this is why your commit messages matter - they tell a story.
  - 'Files changed' will let you see the actual code in several different formats. You also can make line level comments from this view.

### Edit on GitHub
**How to edit a file on GitHub**
- To edit a pull request file, you use the `files changed` view and click the `edit` icon.
- Once you've made changes, create a new commit on the bottom of the page. 
- Make sure you commit to the correct branch

### Merging Pull Requests
**Pull requests**
- During class, please do not close or merge any pull requests other than your own.
- On your own pull request, if all is green and there are no conflicts, go ahead and merge your branch.
- After merging a branch, it's part of the `master` branch and good practice is to delete it.
  - This is a major difference between Git and some older version control systems. In Git, branch often, merge often, and delete branches often.
- Back at the command line, we need to pull down the changes from GitHub.com in the remote repository.
   - `git checkout master`
   - `git pull`
   - `git branch --merged`
   - `git branch -d <branch-name>`
   - `git fetch --prune`
- Configure your settings to do this by default by typing `git config --global fetch.prune true`

### View Local Changes
**Local Diffs**
- View local diff diagram [here](https://services.github.com/kit/modules/CONT-CLI-11_Viewing-local-diffs.html)
- `git diff`: See local changes between working, staging, and history
- If we have added more changes to a file that we've already created, we can see differences between them with `git diff`
- Add to a file just for this example: `echo "Here is one line of text" >> file2.md`
- See status: `git status`
- Stage the file: `git add .`
- `git commit -m "commit message"`
- See status: `git status`
- Add more text: `echo "Here is another line of text" >> file2.md`
- Stage: `git add .`
- More text: `echo "Third line of text" >> file2.md`
- See differences with `git diff`
  - `git diff`
  - `git diff --staged`
  - `git diff HEAD`

### Local History
- Use `git log` to view the history of the repository
- `git log` will show commits from your own local repository, but also changes made by other collaborators 
- Experiment with different option switches to view history:
  - `git log`
  - `git log --oneline`
  - `git log --oneline --graph`
  - `git log --oneline --graph --decorate`
  - `git log --oneline --graph --decorate --all`
  - `git log --stat`
  - `git log --patch`
- Use the up and down arrows or press enter to view additional log entries. Type q to quit viewing the log and return to the command prompt.

### Fixing Commit Mistakes
- Change a commit message with `git commit --amend`

### Streamline Workflow With Aliases
- Set up an alias in configurations: `git config --global alias.<desired-alias> "the long version of the command that you want the alias to run, without git at the beginning, and with the desired flags"`

### Workflow Review Project: GitHub Games
**Fork and Pull Workflow**
- There are two types of accounts on GitHub: User and Organization
- We are forking (copying to our own accout) from the organization [GitHub School](https://github.com/githubschool)
- Navigate to [the github-games repository](https://github.com/githubschool/github-games)
- Fork the repository by clicking the `fork` button on the top right hand side of the browser view
- Navigate to your own fork of the repository. At the top of the page, it should say `your-user-name/github-games`, NOT `githubschool/github-games`
- Clone your repository to your local environment by copying the HTTPS link in your browser and typing `git clone <your-URL>` into your terminal
- Type `cd github-pages` to enter the repository locally

**Make local changes**
- Create a new branch and checkout to the branch at the same time by typing `git checkout -b readme-update`
- Edit the `readme.md` file with your text editor so the link on line 5 reflects your username instead of `githubschool`
- Save those changes, and exit the text editor
- Type `git status` to see your current branch and current stages of each file

**Share changes to GitHub**
- Type `git add readme.md` to move your files from working to staging
- Type `git commit -m "update link in readme"` to move files to history
- To push the changes to the remote repository in the correct branch to reflect your local branch, type `git push -u readme-update`.
- See your changes on GitHub.com

**Change the colors**
- Checkout to the shape-colors branch: `git checkout shape-colors`.
- Open `inde.html` locally.
- Around line 115, change the colors of the block. 
- Save the file and close your text editor.
- Add the changes: `git add -A`
- Commit the changes: `git commit -m "Enter your commit message here"`
- Send changes up to GitHub: `git push`

**Create your Pull Request**
- On GitHub.com, navigate to your own repository of githubgames.
- Click 'pull request'. Make sure the fork is your own copy for both comparisons, and  the 'Base: gh-pages' and 'Compare: shape-colors'.
- Click 'Create pull request'.
- See that there's a merge conflict where normally there would be a big, green button.
- Update your remote: `git pull`
- We are going to do a 'reverse merge', merging the functional main branch into our feature branch to resolve the merge conflict.
- Merge changes locally: `git merge gh-pages`.
- Merge conflict! Open `inde.html` in your favorite text editor and look for the merge conflict markers. 
- Delete one copy of the code as well as the merge conflict markers. 
- Save and close.
- Type `git status` to see the current status of your files.
- Commit the changes: `git commit -m "Enter commit message"`.
- Push up to GitHub: `git push`.
- Checkout back to our main branch: `git checkout gh-pages`
- Merge our changes with a recursive merge: `git merge --no-ff shape-colors`
- Push the changes up to GitHub: `git push`
- Go back to GitHub.com to see how the merge conflict has updated on the pull request. 
- Merge the pull request and delete the branch.

**Clean up the local environment**
- Make sure you have all of the remote tracking branches: `git pull --prune`
- See what branches are merged: `git branch --merged`
- Delete branches that have been merged: `git branch -d shape-colors stats-update`

### Reverting Commits
- `git revert` creates a new commit that is the exact opposite of the selected commit. This is important to note when thinking about impact on history!
- Revert a commit by typing `git revert <first-4-of-commit#>`.

### Fixing the broken game
- See the commit history: `git lol`.
- Find the commit where index.html was renamed to inde.html and copy the first 4 characters of that commit ID
- Revert that commit: `git revert <first-4-characters>`.
- Complete the commit message in your text editor, save, and close.
- Push your local changes to the remote repository: `git push mygame`.
- See your working game by going to the new link in the README on your remote repository.


### Helpful Git Commands
- We made a new file, and renamed it with `git mv`
- Remove files with `git rm`

### Rewriting History With Git Reset
- `git reset` moves the branch pointer along the current branch
- To practice, create a new branch: `git checkout -b <demo-branch-name>`
- Add text to the README with: `echo 'lorem ipsum' >> README.md`
- Commit these changes with `git commit -am"add first dummy line`
- Add more files
  - `echo 'a second line' >> README.md`
  - `git commit -am"a second line"`
  - `echo 'a third line' >> README.md`
  - `git commit -am"a third line"`
- See your recent log history: `git lga-5`
- Reset soft back to one of the earlier commits: `git reset --soft <first 4 of commit ID>`
- See that log: `git lga -5`
- Check our status to see what is staged: `git status`
- `git diff --staged`
- `git commit -m"add additional two lines"`
- `git reset soft` moves head and moves the files back to staging
- The default for `git reset` is `git reset --mixed`.
- Try it with `git reset <first four of commit ID>`
  - Don't forget to use `git lga -5` and `git status` to see how it works
- Now, let's use `git reset --hard <first 4 of commit ID>`
  - Warning: If you `git reset --hard` and there are uncommitted changes, they will be gone forever. :( 
- See how these changes work with `git log --oneline`, `git status`, and `cat README.md`

- In case you were worried that `git reset` had done some damage to your commits, you should know about `git reflog`
- `git reflog` shows every place your HEAD has been, including commits and resets. 
- This means you can `git reset` **back** to the commits you just got rid of!
- Warning: The commits in the reflog do not live forever!
  - Reflog information exists only 30-90 days based on your settings.
  - Reflog information is only local - not on the remote repository or any other collaborator's repositories


### Git cherry-pick
- This command, `git cherry-pick` is not part of the every-day workflow
- `git cherry-pick` will bring back specific commits that may have been undone with `git reset` 
- It's also used to grab a single commit off of a feature branch and replay it on master.
- Practice by typing `git cherry-pick <commit-ID>` of a commit that has been undone
- It's important to only use `git cherry-pick` with commits that have not been pushed to a remote repository as it changes the commit ID of the same information

### Merge Strategies: Rebase
**About Rebase**
- The `rebase` command enables you to modify your commit history in a variety of ways.
- For today’s class, we’ll be using interactive rebase: `git rebase --interactive`, or git `rebase -i` for short.
- Because changing your commit history can make things difficult for everyone else using the repository, it’s considered bad practice to rebase commits you’ve already pushed to a repository.

**Get ready to practice Rebase**
- Type `git checkout -b rebase-me`
- Create 2-3 new files on your branch (HINT: you can use `touch file1.md file2.md file3.md`)
- `Add` and `commit` each file seperately.
- Type `git checkout master`
- Create 2-3 new files on master (e.g. `touch file4.md file5.md file6.md`)
- Take a look at your history by typing `git log --oneline --graph --decorate --all`

**Begin the Rebase**
- Type `git checkout rebase-me`
- Start the merge by typing `git rebase -i master`
- Your text editor will open, allowing you to see the commits to be rebased
- Save and close the `rebase-todo`
- Watch your rebase happen on the Command Line

**Check it Out**
- See your cool changes by typing `git log --oneline --graph --decorate --all`
- Go back to master by typing `git checkout master`
- Merge your changes in to master by typing `git merge rebase-me`
