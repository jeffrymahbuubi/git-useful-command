# Git Submodules Initialization

A Git **submodule** allows you to include one Git repository inside another as a dependency. It keeps the external repository as a part of your project, but the external repository maintains its own history and independence.

There may be a more efficient way to reference someone else's repository, but I find using `git submodule` effective. It allows easy access to another repository with just a click, which is useful when I frequently need to reference others' work.

## 1. Steps to work initially with Repository as a Submodule

```bash
# Add the submodule
#i.e., git submodule add https://github.com/StChenHaoGitHub/1D-deeplearning-model-pytorch 1D-deeplearning-model-pytorch-main
git submodule add <repository_link> <name_of_folder>
git submodule init
git submodule update

# Stage and commit the new submodule
git add .
git commit -m "Added 1D-deeplearning-model-pytorch as submodule with correct name"

# Push the changes
git push origin main
```

## 2. Steps to Work with a Forked Repo as a Submodule

This step is quite similar to step number one, where we want to fork another person's repository and use it as a submodule in our own working repository.

```bash
# Go to the root directory of your main repository and run:
git submodule add git@github.com:<your-username>/<forked-repo>.git path/to/submodule

# Initialize and Clone submodules
git submodule init
git submodule update

# Work with submodule
cd path/to/submodule
# Make changes, commit, and push to the submodule's repository
git add .
git commit -m "Updated submodule content"
git push origin main

# Update the submoudle in the main repository, In the main repository, go to the submodule directory and pull the latest changes:
git submodule update --remote --merge

# Then, go back to the root directory of your main repository and commit the updated submodule reference:
git add path/to/submodule
git commit -m "Updated submodule to the latest version"
git push origin main
```

Then the next time you work with the submodule, you just need to repeat this step:

```bash
# Work with submodule
cd path/to/submodule
# Make changes, commit, and push to the submodule's repository
git add .
git commit -m "Updated submodule content"
git push origin main

# Update the submoudle in the main repository, In the main repository, go to the submodule directory and pull the latest changes:
git submodule update --remote --merge

# Then, go back to the root directory of your main repository and commit the updated submodule reference:
git add path/to/submodule
git commit -m "Updated submodule to the latest version"
git push origin main
```
