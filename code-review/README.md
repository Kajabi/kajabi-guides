Code Review
===========

A guide for reviewing code and having your code reviewed at Kajabi.


Principles
----------

* Ask for clarification. ("I didn't understand. Can you clarify?")
* Ask questions; don't make demands. ("What do you think about naming this
  `:user_id`?")
* Avoid selective ownership of code. ("mine", "not mine", "yours")
* Avoid using terms that could be seen as referring to personal traits. ("dumb",
  "stupid"). Assume everyone is intelligent and well-meaning.
* Keep reviews and comments about the code.
* Pull in people in comments you think might provide useful feedback, by adding
  @username for a mention.
* Be polite and respectful.
* Don't use sarcasm.
* Don't use hyperbole. ("always", "never", "endlessly", "nothing")
* If a comment/reply thread grows long, or there is confusion in the discussion,
  consider talking in person.

Having Your Code Reviewed
-------------------------

* Use the [GitHub CLI](https://github.com/github/hub) to convert an existing issue into
  a pull request. The command is `hub pull-request -i <issue #>`.
* Include documentation in the review description.
* Include instructions for testing the feature ("run this migrate task and then visit
  the affiliate dashboard for a User")
* Review your own code before requesting review from someone else.
* Request a review by adding the `review` tag and selecting a relevant reviewer
  from GitHub's "Reviewers" list.
* Avoid rebasing a branch and repushing while a review is in process.
* Be grateful for a reviewer's suggestions. ("Good call. I'll make that change.")
* Try to respond to every comment.
* Use a todolist in the issue or a comment if you want to track ideas you have
  towards fixing requested changes.
* Explain why the code exists. ("It's like that because of these reasons.")
* Don't be shy getting a reviewer's attention if you think they may have lost
  track of your review.

Reviewing Code
--------------

* Adopt a mindset that you, as a reviewer and maintainer, are as responsible
  for the code as the author of the code.
* Identify ways to simplify the code while still solving the problem.
* Offer alternative implementations, but assume the author already considered
  them. ("What do you think about using a custom validator here?").
* See if there's anything that looks like it would be worthy of a followup issue,
  and work with the author via comments on identifying followups.
* Ask clarifying questions to seek the author's rationale.
* Specific things to always look for in our codebase:
  * Areas of code that should be wrapped in feature checks, or features
    missing a check entirely where one could be helpful.
  * If database migrations are taking place, and how they will impact a production deploy.
      * How big is the table they apply to?
      * What types of locks will occur?
      * Will `null: false` additions conflict with production data?
      * Does the `db/schema.rb` file look proper? Was it checked in? Did anything sneak in
        from an unrelated feature branch?
  * Hardcoded English that may require translation in the feature or a followup.
  * Images and similar assets that may have bypassed linting, especially
    images for size efficiency.
  * ENV flags that may have been added by the feature.
* After reviewing the code, manually test the code in the browser, console, or
  background job as applicable. If this is challenging, consider sitting down
  with the author, and have them give you a Q&A style demo.
* Sign off on the pull request with a :+1:, remove the `review` label and
  apply a `thumbsup` label
