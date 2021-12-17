# git-playground

## Feature One

## Feature Two

## Feature Four

## Steps

* Generate PR for a feature branch to dev
* When approving/merging the PR/branch, squash and merge
* This creates a new merge commit on dev that contains all the commits
* Generate a PR for the group of features (a release) to main
* When approving/merging the PR/branch, merge
* This creates a new merge commit that contains the features as sub-commits
* At this point dev will be 1 commit behind master (no commits ahead)
* So, simply merge master to dev
* Dev and Master will be in sync and with the same tip commit.
