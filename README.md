# GitHub Tutorial

_by Nick Irizarri_

---
## Git vs. GitHub
The difference between _Git_ and **Github** is that _Git_ is a file manager and is used to keep track of files that you make changes to, while **Github** is the service that holds all of your _Git_ repositories and allows people to make pull requests (changes) to them. 

---
## Initial Setup
To make a **Github** account, you will need to :
1. Go to [Github](https://github.com/join?source=header-home) and sign up with your email, username, and password. 
2. Then click *continue* and choose the free plan. (Unless you want to pay the $7/month for extra stuff) 
3. Next you can complete the quick survey to "tailor your experience". However, if you don't want to do it you can skip this step. 
4. Yay you made a **Github** account!!!

Next you will need to set up your SSH Key.

You can find it in c9.io/Yourusername > Gear Icon > SSH Keys > Then copy the first SSH key, and hop over to [here](https://github.com/settings/keys) assuming you are already logged in.

Now click on *New SSH Key* and enter a title and then paste in your copied SSH key from Cloud9.

After that, press *Add SSH Key*, and you have successfully established an SSH connection between Cloud9 and your GitHub account.

---
## Repository Setup
When you setup your repository,  you will need to have _Git_ initialized in order for it to work. This would look like `git init` . However, do not use this in your ~/workspace ! If you do by accident use `git init` where you didn't want to, you just need to type ```rm -rf .git``` and then re-initialize git where you wanted it to be. Now, to make a new **Github** repository, click "New Repository" and then name it and then create it. 

### Forking a Repository
To Fork and clone a repository, go to the repository that you plan on forking and then select Fork. It looks like a stethoscope. From there you can clone with SSH and copy and paste the new link into your command line (cloud 9). You will need to use `git clone` and then paste the link that should have your username in it, NOT the username of the original person (unless you only want to Fork the repo).

---
## Workflow & Commands
Lets Recap! The commands you will be constantly using are :
- `git add .`   = this is how you add files to the stage. It gets prepared for the snapshot / commit
- `git commit -m`  = this is how you will commit the file. You will add a commit message afterwards so you know what you have edited.
- `git push`    = this is how you send your changes to the **Github** remote where you can share it with other people.
- `git status` *  = this is a command you will use as much as the ones above. It will tell you what is happening in the working directory and stage area. Then you can see the changes that have been staged or not. It can also tell you if _Git_ sees what is going on.

---
## Rolling Back Changes
There will be a lot of times where you make mistakes but don't worry, there are ways to revert these mistakes.

If you want to undo a commit, run `git reset HEAD~`. It will undo the previous commit and will unstage the files that were added on the stage. However, any changes that you have made in the files will be kept intact.

You can check this by running `git status`. You should see that your branch is behind `x` commits. If you want to undo all the changes from the files after you have ran `git reset HEAD~`, run `git checkout -- FILENAME | .` to discard changes for one file with changes or all files with changes.
