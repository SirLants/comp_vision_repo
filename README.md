# comp_vision_repo
Repo for Lance, Aneesh, and Bruno for facial recognition project

This is our README, here we can store our file structure and any important commands for reminding (such as how to pull down node.js files)

A nice list of Git Commands can be found here
https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html



-------------------------------------------------------------------------------------------

To get your repo set up here is what you are going to want to do.

Before you do anything else:
Make sure you have Git Bash installed on your computer. If you don't, go download it.
If you want the GUI and stuff that is great, but learning command line git is super useful. That is all I will specify here.

Also make sure that you have a Git account setup. If you are reading this you should already have one.

Also, in case this needs to be said, watch a YouTube video on what Git is if you don't know what it is.
Its basically just a virtual directory that has a bunch of diff functionality built in.
Makes it easy to keep up-to-date versions of code and to not completely fuck anything up.

Initial Setup:
To label yourself properly, type:
git config --global user.name "Your name here"
git config --global user.email "your_email@example.com"
We also need to get you an SSH key assocation so you don't have to type in your git login info every time.
First, check if you already have an SSH key. Type:
ls -al ~/.ssh
If nothing pops up:
ssh-keygen -t rsa -C "your_associated_git_email@example.com"
press enter through the rest, DONT change the directory for where the SSH goes. add a passcode if you want.


If you see id_rsa.pub: 
skip to CONTINUE

CONTINUE
Go to the .ssh directory, open id_rsa.pub in notepad, and copy the file.
Go to your github profile, go to SSH keys, and add a new SSH key. paste in the contents of the id_rsa.pub file.
If this all worked, you should be able to type in ssh -T git@github.com and see a "Hi Username!" response.

FINALLY
make sure ssh-agent is running, type:
eval $(ssh-agent -s)
This should spit out a pid (if you have taken 451 you know this is the thread the process is running on)
Provided that all works, type:
ssh-add ~/.ssh/id_rsa
If this doesn't work you fucked something up. HMU.

First:
Open up Git Bash, or on Mac open Terminal. Navigate to whatever directory you want to clone the repository into.
When you are in said directory, copy and paste this command:
git clone git@github.com:SirLants/language_is_fun_repo.git
You should see a bunch of shit happen and you should now be able to type "ls" and see our repo. If your ssh isn't setup properly this may have issues.
Open the repo directory.
You did it.
If any of this didn't work HMU homie.

Second:
You can now see our repository just like any normal directory, this particular directory is just tracked by Git.
Go back to your bash.
Don't add code or push code in master. Doing so will earn you a bitch slap.
Instead, branch off of master, type:
git checkout -b <name_of_branch> // this will create your branch and open your branch at the same time
alternatively you can type:
git branch <name_of_branch>
git checkout <name_of_branch> // this does the same thing just in two steps

Third:
Now that you are in your branch, go ahead and type:
git status // this is the equivalent of ls in git, you'll type this a lot
If you haven't made any changes yet, nothing should pop up.
Go ahead and edit the readme.md file with anything bogus, add "<name> TEST", at the bottom of the file, or whatever. Save your changes.
Type git status again. This time shit will pop up. You have stuff that is different than master!
Type "git add <filename>" // this is case sensitive
Type git status again. Your file should change from red to green.
Type:
git commit -m "MY FIRST COMMIT YAY"
Type git status. Nothing should happen again, you just did your first commit. Grats.

Fourth:
Now you have a commit, but that commit is only on your local machine, the great repository in the sky has not yet been gifted with your awesome code.
To change this, type:
git push origin <branch_name>
Some shit should pop up. If it asks you for your username you didn't set up SSH properly.
Now go to our GitHub repository on the GitHub website.
Your branch should automatically show up on the main screen and offer to pull request.
Go ahead and do that. Make sure you are going from your branch to master. Type a useful message that highlights what you are doing with this pull request.
When your code isn't completely trivial, like in this tutorial, let everyone know that you just added new code that needs reviewing in the "announcements" channel.

Finally: 
Once your pull request is approved and merged you no longer need your local branch, because all of its changes are now in master.
To navigate back to master, type:
git checkout master
Now that you are in master, type:
git pull
This will pull any and all changes from the repository in the sky down to your computer, including the changes that were just merged into master.
To delete your branch, type:
git branch -d <name_of_branch>
If you don't git pull this will say "your changes haven't been merged", that is just because your local machine can't see the changes in the repository yet.
And that is all! I think!
----------------------------------------------------------------------------------------------



File Structure (for later):
-README
-index.html
-bla bla bla bla
--sub bla bla
---bla.html
--sub bla bla
---bla.css
-bla bla bla
--sub bla
---bla.js