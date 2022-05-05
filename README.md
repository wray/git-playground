# git-playground

## Feature One

## Feature Two

## Feature Three

## Feature Four

## Feature Five

## Feature Nine

## Life of an issue
* Team Lead(s): Create issue and link to team board (lands on To Do)
* Team Lead(s): Groom issue:
  * Fill in template
  * Required: At least circle impact on top-level diagram
  * Bonus points for identifying systems and interfaces (by id) and/or deployment resources/alerts
  * Bonus points for suggesting high-level verification
  * Add to relevant L2 list and tag with SO's (if not assume all inherited from L2)
  * Back reference L2 in issue
  * Bonus Points for providing best case/worst case WIP cycle time
  * Bonus Points if there is already a draft RC that should include this work
  * create branch *if on latest GH version*
* Team Lead(s): In issue untag "not ready" to signal groomed
* Dev: "Grab" issue:
  * Assign self and partners if pair+ solving 
  * *in issue choose in progress to signal wip* -- for repos with a develop branch
* Dev: Immediately checkout branch (use branch if already created and linked otherwise create)
* Dev: Push a documentation/placeholder change and open draft PR against develop (use `fixes` or `closes` keyword in description to link issue to close for repos without a develop branch)
* Dev (toil): Back in issue, refresh the issue. If the PR is not automatically linked, manually link it (which will be the case current GHE state for repos with a develop branch)
* Dev: On PR - Deliberately add at least two peer reviewers and one lead
* Dev: When all work is done, including design, tests, regression, release notes, mark as ready-for-review
* Dev: Respond to requests for changes until approval minimums are met
* Team Lead(s): SQUASH and merge
* Team Lead(s) / Dev: Move issue to "Done" on Team Board, but do not close issue.

## Release Steps
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
