Code Review
===========

A guide for reviewing code and having your code reviewed at Kajabi.


Principles
----------

* Ask for clarification. ("I didn't understand. Can you clarify?")
* Ask good questions; don't make demands. ("What do you think about naming this
  `:user_id`?")
* Avoid selective ownership of code. ("mine", "not mine", "yours")
* Avoid using terms that could be seen as referring to personal traits. ("dumb",
  "stupid"). Assume everyone is intelligent and well-meaning.
* Keep reviews and comments about the code, avoid making things personal
* Pull in people in comments you think might provide useful feedback, by adding
  @username for a mention
* Keep questions and comments polite
* Don't use sarcasm.
* Don't use hyperbole. ("always", "never", "endlessly", "nothing")
* If a comment/reply thread grows long, or their is confusion in the discussion,
  consider talking in person (face to face, or Slack video)

Having Your Code Reviewed
-------------------------

* Use hub to convert an existing issue into a review ticket
* Include documentation in the review description or a comment if testing
  the review involves novel concepts ("run this migrate task and then visit
  the affiliate dashboard for a User")
* Avoid rebasing a branch and repushing while a review is in process
* Be grateful for a reviewer's suggestions. ("Good call. I'll make that
  change.")
* Try to respond to every comment.
* Use a todolist in the issue or a comment if you want to track ideas you have
  towards fixing requested changes.
* Explain why the code exists. ("It's like that because of these reasons.)
* Merge once you feel confident the code could be safely deployed, typically
  with a rebase followed by --no-ff merge.
* Don't be shy getting a reviewers attention if you think they may have lost
  track of your review.

Reviewing Code
--------------

* Adopt a mindset that you are as responsible for the code as a reviewer and
  maintainer, as the author of the code.
* Identify ways to simplify the code while still solving the problem.
* Offer alternative implementations, but assume the author already considered
  them. ("What do you think about using a custom validator here?").
* See if there's anything that looks like it would be worthy of a followup issue,
  and work with identifying followups with the author via comments.
* Ask clarifying questions to seek the author's rationale.
* Look for areas of code that should be wrapped in feature checks, or features
  missing a check entirely where one could be helpful.
* Note if database migrations are taking place.
* Understand how the migrations in place will impact a production deploy. How big
  is the table they apply to, what types of locks will occur, will `null: false`
  additions conflict with production data.
* Look for hardcoded English that may require translation in the feature or a
  followup.
* Look for images and similar assets that may have bypassed linting, especially
  images for size efficiency.
* ENV flags that may have been added by the feature.
* Check if the db/schema.rb file looks proper, or if anything snuck in from an
  unrelated feature branch.
* After reviewing the code, manually test the code in the browser, console, or
  background job as applicable. If this is challenging, consider sitting down
  with the author, and have them give you a Q&A style demo.
* Sign off on the pull request with a :+1:, remove the `in progress` label and
  apply a `thumbsup` label
