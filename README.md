# GitHelper

## How-To simple Commands

### How to clone a repository:

Create a local directory to hold the repo
```
mkdir koret
cd koret/
```

Go to the website of the repo and get the clone url

![img missing](GitClone.PNG)

clone the repo into your directory
```
git clone https://github.com/SonomaDeepThought/deepintegration-one.git
```

### How to commit changes made

When you commit your code, you have to choose which files to commit. This is often a two-step process that requires the user to call _git add ._ followed by _git commit -m "message"_ but for our purposes we can condense this to a single command
```shell
git commit -am "message"
```
The -a means:  _stage_ all modified files before committing. Essentially, ensure all modified  files are committed. 


### How to checkout a branch

The first thing you do before working is check which branch you are working from
```
git status
```
![img missing](GitStatus.PNG)


-OR-

git branch will list all the branches as well as the current branch
```
git branch
```

![img_missing](GitBranch.PNG)

Once you see which branch you are on, you can change to the branch you would like to work on
```
git checkout branchname
```


### How to create a branch

To create a new branch from a branch (this is what we do since we only work off dev)
```
git checkout -b newBranch oldBranch
```


To be able to push your work in the new branch to GitHub we have to set the upstream
```
git push --set-upstream origin newBranch
```
Now anyone with access to the repo should be able to see and access the newly created branch on the website. 


### How to merge a two branches
Now that you have completed a feature, you will need to merge the feature into the branch we branched from. In order to do this you want to ensure that you are on the branch you want to merge, in this case newFeature.


```
git checkout newFeature
```

Once on our feature that we want to merge, we merge the dev branch into it

```
git merge dev
```

This can produce merge conflicts that you may need to fix. This is quite in depth so I will just provide a link to a guide.
```
https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/
```

Once your feature has dev merged into it, we need to change to the dev branch and merge with the newFeature. 
```
git checkout dev
git merge newFeature
```

The reason for doing this in a 2-step process is that we want to find and squash issues with merging in the feature branch and not in the dev branch. We want to maintain working dev and master branches. 
