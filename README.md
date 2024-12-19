This is the git repo of some of the folders in my local Documents. I followed the approach described here. 

[https://stackoverflow.com/questions/61512209/how-do-i-create-a-git-repo-from-multiple-directories](https://stackoverflow.com/questions/61512209/how-do-i-create-a-git-repo-from-multiple-directories)






# To init the repo

```
echo "# documents" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:andreavitaletti/documents.git
git push -u origin main
```

```
git remote show origin
```

# To download only specific content

```
# Create a directory, so Git doesn't get messy, and enter it
mkdir code_from_git && cd code_from_git

# Start a Git repository
git init

# Track repository, do not enter subdirectory
git remote add -f origin https://github.com/andreavitaletti/IoT_short_course

# Enable the tree check feature
git config core.sparseCheckout true

# Create a file in the path: .git/info/sparse-checkout
# That is inside the hidden .git directory that was created
# by running the command: git init
# And inside it enter the name of the sub directory you only want to clone
echo 'PlatformIO/Projects/power' >> .git/info/sparse-checkout

## Download with pull, not clone
git pull origin main
```
