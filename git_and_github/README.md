# kajabi-github-flow

The following are some guidelines for how developers at Kajabi work on new
features using git and GitHub. Note these are strong guidelines, but rarely
100% rules, but they are pretty easy to follow 99% of the time.

## Guidelines for using github issues

* Assign an issue to yourself if you want to work on it.
* Prefer tasks with an upcoming milestone if possible.
* When you start working on the task, apply the "in progress" label.
* Open a pull request when your task is ready, or if you have made substantial
  progress and want some early feedback.
* When your feature is ready for a full review and you are looking for it to merge
  into master, remove the "in progress" label and apply the "review" label.
* If your review has been up a few hours and people seem to be available, it's possible it
  was overlooked.  Always be nudging people to review your open PRs.
* If you are freed up and spot something that is assigned but idle, don't be shy! Ask the
  asignee about it, maybe you can take it off their hands and get it completed sooner.

## Guidelines for using git and branches

* `master` is the mainline development branch.  Code merged to master should not break a deploy.
* `production` is our tracking branch we use to deploy.  Commits are not made into `production`, we
  do a standard merge from `master` to `production` for a deploy.
* bugfixes should target `master`
* Work on new features should be done in feature branches off of `master`.
* When possible, prefer features branches in the format `jad-1005_some_feature_description`.
  * jad - your initials, jad for Jane Allison Doe, for example
  * 1005 - the issue number for the feature on github
  * some_feature_description - a brief feature description, it's a nice hint to you and others.
* Prefer rebasing feature branches pre-merge into `master` whenever possible.

### About our rebase & merge strategy

tl;dr Always be rebasing, avoid the GitHub merge button.

If possible, the following flow should be used for a new feature.  This prevents work from other features
from being mingled with work from your feature in the master branch.  It creates a history on master that
is much cleaner to read when tracking work done on a feature.

If you are not comfortable with git or some of these commands, please ask someone to help out!

* git checkout master
* git pull --rebase origin master
* git checkout -b jad-1005_some_feature_description
* Work, review, thumbs up, prepare to put in master
  * git push -u origin jad-1005_some_feature_description
* git checkout origin master
* git pull --rebase origin master
* git checkout jad-1005_some_feature_description
* git rebase master
  * Resolve conflicts if necessary
  * git push -u --force origin  jad-1005_some_feature_description
* git checkout master
* git merge --no-ff jad-1005_some_feature_description
* git push origin master
* cleanup after yourself when you are ready
  * git branch -d jad-1005_some_feature_description
  * git push origin :jad-1005_some_feature_description

## Code makes it into `master` via code reviews

* Code should generally by reviewed by someone that didn't work on the feature before merging into master.
  If the code was developed in pairing, prefer a review from someone other than the pair
* When reviewing code, prefer inline notes when possible to ask questions about the code.  If it's a general
  question, you can leave it as a general comment.
* When the feature branch maintainer has addressed issues nicely (or filed followup issues), let them know it's
  ready to go by:
  * adding a comment that contains a thumbs up +1 emoji (:+1:)
  * removing the "review" label and applying the "thumbsup" label
* Keep track of code you review and thumbsup.  Sometimes it's easy to miss an email or notification, help out
  by reminding your coworkers if it looks like it slipped by.
* The feature maintainer typically handles the rebase/merge back into master.  If they are tied up, out, etc,
  it can be a nice gesture to offer to merge it for them.  Let them know!
* There is no rule about who can merge to master.  Be smart, not shy.
