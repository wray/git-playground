# git-playground

## Feature One

## Feature Two

## Feature Three

## Feature Four

## Feature Five

## Steps
Note, I am proposing the tagging strategy we had used back in the day for alfa releases.

* Generate PR for a feature branch to dev
* When approving/merging the PR/branch, squash and merge
* This creates a new merge commit on dev that contains all the commits
* Generate a PR for the group of features (a release) to main
* When approving/merging the PR/branch, merge (only)
* This creates a new merge commit that contains the features as sub-commits
* Tag that commit on main: 
  * `git tag -a v1.0 -m "Release 1.0"`
  * `git push origin v1.0`
* At this point dev will be 1 commit behind master (no commits ahead)
* So, simply merge master to dev
* Dev and Master will be in sync and with the same tip commit (the same commit that has been tagged).
* Now, you can go back and create the release from the tag and autogenerate the notes
