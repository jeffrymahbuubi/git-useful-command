# Git Submodules Initialization

A Git **submodule** allows you to include one Git repository inside another as a dependency. It keeps the external repository as a part of your project, but the external repository maintains its own history and independence.

There may be a more efficient way to reference someone else's repository, but I find using `git submodule` effective. It allows easy access to another repository with just a click, which is useful when I frequently need to reference others' work.

```bash
# Add the submodule
#i.e., git submodule add https://github.com/StChenHaoGitHub/1D-deeplearning-model-pytorch 1D-deeplearning-model-pytorch-main
git submodule add repository_link name_of_folder
git submodule init
git submodule update

# Stage and commit the new submodule
git add .
git commit -m "Added 1D-deeplearning-model-pytorch as submodule with correct name"

# Push the changes
git push origin main
```
