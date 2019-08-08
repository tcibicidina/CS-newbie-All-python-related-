# Git Intro

This note will serve as an intro to setting up GtiHub (remotely and locally) while I learn.
Specifically, this tutorial works for the windows operating system.

## Initializing

Here I am going to record all the command I typed /other steps I did to create this whole new repository!

- step 0. Yes, I started from hitting on the new button under 'repositories'
- step 1. Maybe stupid but github intro does not tell you ....open the git bash and `cd` into a location
  you want this repository to be in! if *cd f:/*  does not work, try *cd f:* or just *f:.*
- step 2. Ok now you can type in this bunch of code github nicely ofers to us dummies. It first writes
  your repo's name into the `README.md` file (which you could always update later). Then `git init` tells
  git that this is going to be linked to a repository. Then the `git add` and `git commit` statements
  adds this file to your local staging zone. `git remote add` is an operation that you may only need to
  do once, if you do not plan to use multiple repos to track the same stuff. It tells your local git which
  remote repo it links to. Finally by `git push`, you are pushing your local stuff to the remote repo.
```
echo "<your repo's name>" >> README.md
git init
git add README.md
git commit -m "<your commit's name>"
git remote add origin https://github.com/<your git acount</<your repo's name>.git
git push -u origin master
```
- step 3  Now update the readme file as you like. Once you are done, save your changes, and type in
the following 3 lines into your git bash.
```
git -add u
#add in all changes
git commit -m 'test'
#check point a commit
git push -u origin master
#push to git
```
now refresh your repository and see the changes!

- step 4 A future step 4 is that if you are cooperating with somebody else, try pull all the changes
she / her may have made before you edit your file (every time!) using the following commands. Or,
alternatively, you can always merge their changes with yours, but this sometimes involves conflicts.

```
git pull
# obtain the newest version of the remote branch

git status 
#check all changes made
```
Great! Now we finished our very own first thing first! 

## To-do's
I still need to figure out:

- [ ] Why every time I try to push / pull my gitbash keeps asking for my username and password? Is there
a way to figure it out one time for all? I am sure there is!
- [ ] How does `.gitignore` work
- [ ] Learn the options for `git status`
