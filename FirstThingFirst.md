# First thing first
Yet, I still need to admit that I'm on the very beginning of the github learning curve, so I'm going to record everything I learnt / yet to learn here.

## Create a new reporsitory, initial settings, blah blah blah...
Here I'm going to record all the command I typed /other steps I did to create this whole new repository!
- step 0. Yes, I started from hitting on the new button under 'repositories'
- step 1. Maybe stupid but github intro doesn't tell you ....open the git bash and cd into a location you want this repository to be in! if *cd f:/*  does not work, try *cd f:* or just *f:.*
- step 2. Ok now you can type in this bunch of code github nicely ofers to us dummies. It echoes the repo to the selected location in your PC, add a readme file, commit your very first update, add remote origin, and push your updates to git (Yes, I don't fully understand them so I could be wrong!)
```
echo "<your repo's name>" >> README.md
git init
git add README.md
git commit -m "<your commit's name>"
git remote add origin https://github.com/<your git acount</<your repo's name>.git
git push -u origin master
```
- step 3  Now update the readme file as you like. Once you are done, save your changes, and type in the following 3 lines into your git bash.
```
git -add u
#add in all changes
git commit -m 'test'
#check point a commit
git push -u origin master
#push to git
```
now refresh your repository and see the changes!

- step 4 A future step 4 is that if you are cooperating with somebody else, try pull all the changes she / her may have made before you edit your file (every time!) using the following commands.

```
git pull
# obtain the newest version of the remote branch

git status 
#check all changes made
```
Great! Now we finished our very own first thing first! 

## Yet to learn!
I still need to figure out
- 1. Why every time I try to push / pull my gitbash keeps asking for my username and password? Is there a way to figure it out one time for all? I'm sure there is!
