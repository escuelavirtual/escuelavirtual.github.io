Contributing
============

.. contents:: Table of Contents

Introduction
------------

Thank you so much for your interest in contributing!. All types of
contributions are encouraged and valued. See the `table of contents`_
for different ways to help and details about how this project handles
them!📝

Please make sure to read the relevant section before making your
contribution! It will make it a lot easier for us maintainers to make
the most of it and smooth out the experience for all involved. 💚

The `Project Team`_ looks forward to your contributions. 🙌🏾✨

Request Support
---------------

If you have a question about this project, how to use it, or just need
clarification about something:

-  Open an issue at
   https://github.com/escuelavirtual/escuelavirtual.github.io/issues or
   in the corresponding repositories
-  Provide as much context as you can about what you're running into.
-  Provide project and platform versions (nodejs, npm, etc), depending
   on what seems relevant. If not, please be ready to provide that
   information if maintainers ask for it.

Once it's filed:

-  The project team will `label the issue`_.
-  Someone will try to have a response soon.
-  If you or the maintainers don't respond to an issue for 30 days, the
   `issue will be closed`_. If you want to come back to it, reply (once,
   please), and we'll reopen the existing issue. Please avoid filing new
   issues as extensions of one you already made.

Report an Error or Bug
----------------------

If you run into an error or bug with the project:

-  Open an Issue at
   https://github.com/escuelavirtual/escuelavirtual.github.io/issues or
   in the corresponding repositories
-  Include *reproduction steps* that someone else can follow to recreate
   the bug or error on their own.
-  Provide project and platform versions (nodejs, npm, etc), depending
   on what seems relevant. If not, please be ready to provide that
   information if maintainers ask for it.

Once it's filed:

-  The project team will `label the issue`_.
-  A team member will try to reproduce the issue with your provided
   steps. If there are no repro steps or no obvious way to reproduce the
   issue, the team will ask you for those steps and mark the issue as
   ``needs-repro``. Bugs with the ``needs-repro`` tag will not be
   addressed until they are reproduced.
-  If the team is able to reproduce the issue, it will be marked
   ``needs-fix``, as well as possibly other tags (such as ``critical``),
   and the issue will be left to be `implemented by someone`_.
-  If you or the maintainers don't respond to an issue for 30 days, the
   `issue will be closed`_. If you want to come back to it, reply (once,
   please), and we'll reopen the existing issue. Please avoid filing new
   issues as extensions of one you already made.
-  ``critical`` issues may be left open, depending on perceived
   immediacy and severity, even past the 30 day deadline.

.. _table of contents: #toc
.. _Project Team: #join-the-project-team
.. _label the issue: #label-issues
.. _issue will be closed: #clean-up-issues-and-prs
.. _implemented by someone: #contribute-code

Request a Feature
-----------------

If the project doesn't do something you need or want it to do:

-  Open an Issue at
   https://github.com/escuelavirtual/escuelavirtual.github.io/issues or
   in the corresponding repositories
-  Provide as much context as you can about what you're running into.
-  Please try and be clear about why existing features and alternatives
   would not work for you.

Once it's filed:

-  The project team will `label the issue`_.
-  The project team will evaluate the feature request, possibly asking
   you more questions to understand its purpose and any relevant
   requirements. If the issue is closed, the team will convey their
   reasoning and suggest an alternative path forward.
-  If the feature request is accepted, it will be marked for
   implementation with ``feature-accepted``, which can then be done by
   either by a core team member or by anyone in the community who wants
   to `contribute code`_.

Note: The team is unlikely to be able to accept every single feature
request that is filed. Please understand if they need to say no.

Project Setup
-------------

So you wanna contribute some code! That's great! This project uses
GitHub Pull Requests to manage contributions, so `read up on how to fork
a GitHub project and file a PR`_ if you've never done it before.

If this seems like a lot or you aren't able to do all this setup, you
might also be able to `edit the files directly`_ without having to do
any of this setup. Yes, `even code`_.

If you want to go the usual route and run the project locally, though:

-  `Install Node.js`_
-  `Fork the project`_

Then in your terminal:

-  ``cd path/to/your/clone``
-  ``npm install``
-  ``npm test``

Rename the file located in the main directory ``.env.example`` to
``.env`` if you haven't already done so.

And you should be ready to go!

.. _label the issue: #label-issues
.. _contribute code: #contribute-code
.. _read up on how to fork a GitHub project and file a PR: https://guides.github.com/activities/forking
.. _edit the files directly: https://help.github.com/articles/editing-files-in-another-user-s-repository/
.. _even code: #contribute-code
.. _Install Node.js: https://nodejs.org/en/download/
.. _Fork the project: https://guides.github.com/activities/forking/#fork

Contribute Documentation
------------------------

Documentation is a super important, critical part of this project. Docs
are how we keep track of what we're doing, how, and why. It's how we
stay on the same page about our policies. And it's how we tell others
everything they need in order to be able to use this project -- or
contribute to it. So thank you in advance.

Documentation contributions of any size are welcome! Feel free to file a
PR even if you're just rewording a sentence to be more clear, or fixing
a spelling mistake!

To contribute documentation:

-  `Set up the project`_.
-  Edit or add any relevant documentation.
-  Make sure your changes are formatted correctly and consistently with
   the rest of the documentation.
-  Re-read what you wrote, and run a spellchecker on it to make sure you
   didn't miss anything.
-  Write clear, concise commit message(s) using `conventional-changelog
   format`_. Documentation commits should use
   ``docs(<component>): <message>``.
-  Go to
   https://github.com/escuelavirtual/escuelavirtual.github.io/pulls or
   in the corresponding repositories and open a new pull request with
   your changes.
-  If your PR is connected to an open issue, add a line in your PR's
   description that says ``Fixes: #123``, where ``#123`` is the number
   of the issue you're fixing.

Once you've filed the PR:

-  One or more maintainers will use GitHub's review feature to review
   your PR.
-  If the maintainer asks for any changes, edit your changes, push, and
   ask for another review.
-  If the maintainer decides to pass on your PR, they will thank you for
   the contribution and explain why they won't be accepting the changes.
   That's ok! We still really appreciate you taking the time to do it,
   and we don't take that lightly. 💚
-  If your PR gets accepted, it will be marked as such, and merged into
   the ``latest`` branch soon after. Your contribution will be
   distributed to the masses next time the maintainers `tag a release`_

.. _Set up the project: #project-setup
.. _conventional-changelog format: https://github.com/conventional-changelog/conventional-changelog-angular/blob/master/convention.md
.. _tag a release: #tag-a-release

Contribute Code
---------------

We like code commits a lot! They're super handy, and they keep the
project going and doing the work it needs to do to be useful to others.

Code contributions of just about any size are acceptable!

The main difference between code contributions and documentation
contributions is that contributing code requires inclusion of relevant
tests for the code being added or changed. Contributions without
accompanying tests will be held off until a test is added, unless the
maintainers consider the specific tests to be either impossible, or way
too much of a burden for such a contribution.

To contribute code:

-  `Set up the project`_.
-  Make any necessary changes to the source code.
-  Include any `additional documentation`_ the changes might need.
-  Write tests that verify that your contribution works as expected.
-  Write clear, concise commit message(s) using `conventional-changelog
   format`_.
-  Dependency updates, additions, or removals must be in individual
   commits, and the message must use the format:
   ``<prefix>(deps): PKG@VERSION``, where ``<prefix>`` is any of the
   usual ``conventional-changelog`` prefixes, at your discretion.
-  Go to
   https://github.com/escuelavirtual/escuelavirtual.github.io/pulls or
   in the corresponding repositories and open a new pull request with
   your changes.
-  If your PR is connected to an open issue, add a line in your PR's
   description that says ``Fixes: #123``, where ``#123`` is the number
   of the issue you're fixing.

Once you've filed the PR:

-  Barring special circumstances, maintainers will not review PRs until
   all checks pass (Travis, AppVeyor, etc).
-  One or more maintainers will use GitHub's review feature to review
   your PR.
-  If the maintainer asks for any changes, edit your changes, push, and
   ask for another review. Additional tags (such as ``needs-tests``)
   will be added depending on the review.
-  If the maintainer decides to pass on your PR, they will thank you for
   the contribution and explain why they won't be accepting the changes.
   That's ok! We still really appreciate you taking the time to do it,
   and we don't take that lightly. 💚
-  If your PR gets accepted, it will be marked as such, and merged into
   the ``latest`` branch soon after. Your contribution will be
   distributed to the masses next time the maintainers `tag a release`_

.. _Set up the project: #project-setup
.. _additional documentation: #contribute-documentation
.. _conventional-changelog format: https://github.com/conventional-changelog/conventional-changelog-angular/blob/master/convention.md
.. _tag a release: #tag-a-release

Provide Support on Issues
-------------------------

Helping out other users with their questions is a really awesome way of
contributing to any community. It's not uncommon for most of the issues
on an open source projects being support-related questions by users
trying to understand something they ran into, or find their way around a
known bug.

Sometimes, the ``support`` label will be added to things that turn out
to actually be other things, like bugs or feature requests. In that
case, suss out the details with the person who filed the original issue,
add a comment explaining what the bug is, and change the label from
``support`` to ``bug`` or ``feature``. If you can't do this yourself,
@mention a maintainer so they can do it.

In order to help other folks out with their questions:

-  Go to the issue tracker and `filter open issues by the ``support``
   label`_ or in the corresponding repositories.
-  Read through the list until you find something that you're familiar
   enough with to give an answer to.
-  Respond to the issue with whatever details are needed to clarify the
   question, or get more details about what's going on.
-  Once the discussion wraps up and things are clarified, either close
   the issue, or ask the original issue filer (or a maintainer) to close
   it for you.

Some notes on picking up support issues:

-  Avoid responding to issues you don't know you can answer accurately.
-  As much as possible, try to refer to past issues with accepted
   answers. Link to them from your replies with the ``#123`` format.
-  Be kind and patient with users -- often, folks who have run into
   confusing things might be upset or impatient. This is ok. Try to
   understand where they're coming from, and if you're too uncomfortable
   with the tone, feel free to stay away or withdraw from the issue.
   (note: if the user is outright hostile or is violating the CoC,
   `refer to the Code of Conduct`_ to resolve the conflict).

.. _Needs Collaborator: #join-the-project-team
.. _filter open issues by the ``support`` label: https://github.com/escuelavirtual/escuelavirtual.github.io/issues?q=is%3Aopen+is%3Aissue+label%3Asupport
.. _refer to the Code of Conduct: CODE_OF_CONDUCT.md

Label Issues
------------

One of the most important tasks in handling issues is labeling them
usefully and accurately. All other tasks involving issues ultimately
rely on the issue being classified in such a way that relevant parties
looking to do their own tasks can find them quickly and easily.

In order to label issues, `open up the list of unlabeled issues`_ and,
**from newest to oldest**, read through each one and apply issue labels
according to the table below. If you're unsure about what label to
apply, skip the issue and try the next one: don't feel obligated to
label each and every issue yourself!

.. _Needs Collaborator: #join-the-project-team
.. _open up the list of unlabeled issues: https://github.com/escuelavirtual/escuelavirtual.github.io/issues?q=is%3Aopen+is%3Aissue+no%3Alabel

+-------------------+-----------------------+-----------------------+
| Label             | Apply When            | Notes                 |
+===================+=======================+=======================+
| ``bug``           | Cases where the code  | If something is       |
|                   | (or documentation) is | happening that        |
|                   | behaving in a way it  | surprises the *user*  |
|                   | wasn't intended to.   | but does not go       |
|                   |                       | against the way the   |
|                   |                       | code is designed, it  |
|                   |                       | should use the        |
|                   |                       | ``enhancement``       |
|                   |                       | label.                |
+-------------------+-----------------------+-----------------------+
| ``critical``      | Added to ``bug``      |                       |
|                   | issues if the problem |                       |
|                   | described makes the   |                       |
|                   | code completely       |                       |
|                   | unusable in a common  |                       |
|                   | situation.            |                       |
+-------------------+-----------------------+-----------------------+
| ``documentation`` | Added to issues or    | Can be combined with  |
|                   | pull requests that    | other labels, such as |
|                   | affect any of the     | ``bug`` or            |
|                   | documentation for the | ``enhancement``.      |
|                   | project.              |                       |
+-------------------+-----------------------+-----------------------+
| ``duplicate``     | Added to issues or    | Duplicate issues      |
|                   | PRs that refer to the | should be marked and  |
|                   | exact same issue as   | closed right away,    |
|                   | another one that's    | with a message        |
|                   | been previously       | referencing the issue |
|                   | labeled.              | it's a duplicate of   |
|                   |                       | (with ``#123``)       |
+-------------------+-----------------------+-----------------------+
| ``enhancement``   | Added to `feature     |                       |
|                   | requests`_, PRs, or   |                       |
|                   | documentation issues  |                       |
|                   | that are purely       |                       |
|                   | additive: the code or |                       |
|                   | docs currently work   |                       |
|                   | as expected, but a    |                       |
|                   | change is being       |                       |
|                   | requested or          |                       |
|                   | suggested.            |                       |
+-------------------+-----------------------+-----------------------+
| ``help wanted``   | Applied by            | Never applied on      |
|                   | `Committers`_ to      | first-pass labeling.  |
|                   | issues and PRs that   |                       |
|                   | they would like to    |                       |
|                   | get outside help for. |                       |
|                   | Generally, this means |                       |
|                   | it's lower priority   |                       |
|                   | for the maintainer    |                       |
|                   | team to itself        |                       |
|                   | implement, but that   |                       |
|                   | the community is      |                       |
|                   | encouraged to pick up |                       |
|                   | if they so desire     |                       |
+-------------------+-----------------------+-----------------------+
| ``in-progress``   | Applied by            | The original PR       |
|                   | `Committers`_ to PRs  | submitter should      |
|                   | that are pending some | @mention the team     |
|                   | work before they're   | member that applied   |
|                   | ready for review.     | the label once the PR |
|                   |                       | is complete.          |
+-------------------+-----------------------+-----------------------+
| ``performance``   | This issue or PR is   |                       |
|                   | directly related to   |                       |
|                   | improving             |                       |
|                   | performance.          |                       |
+-------------------+-----------------------+-----------------------+
| ``refactor``      | Added to issues or    |                       |
|                   | PRs that deal with    |                       |
|                   | cleaning up or        |                       |
|                   | modifying the project |                       |
|                   | for the betterment of |                       |
|                   | it.                   |                       |
+-------------------+-----------------------+-----------------------+
| ``starter``       | Applied by            | Existing project      |
|                   | `Committers`_ to      | members are expected  |
|                   | issues that they      | to stay away from     |
|                   | consider good         | these unless they     |
|                   | introductions to the  | increase in priority. |
|                   | project for people    |                       |
|                   | who have not          |                       |
|                   | contributed before.   |                       |
|                   | These are not         |                       |
|                   | necessarily "easy",   |                       |
|                   | but rather focused    |                       |
|                   | around how much       |                       |
|                   | context is necessary  |                       |
|                   | in order to           |                       |
|                   | understand what needs |                       |
|                   | to be done for this   |                       |
|                   | project in            |                       |
|                   | particular.           |                       |
+-------------------+-----------------------+-----------------------+
| ``support``       | This issue is either  | The label should be   |
|                   | asking a question     | switched to ``bug``   |
|                   | about how to use the  | if reliable           |
|                   | project, clarifying   | reproduction steps    |
|                   | the reason for        | are provided. Issues  |
|                   | unexpected behavior,  | primarily with        |
|                   | or possibly reporting | unintended            |
|                   | a ``bug`` but does    | configurations of a   |
|                   | not have enough       | user's environment    |
|                   | detail yet to         | are not considered    |
|                   | determine whether it  | bugs, even if they    |
|                   | would count as such.  | cause crashes.        |
+-------------------+-----------------------+-----------------------+
| ``tests``         | This issue or PR      | If a PR is pending    |
|                   | either requests or    | tests, that will be   |
|                   | adds primarily tests  | handled through the   |
|                   | to the project.       | `PR review process`_  |
+-------------------+-----------------------+-----------------------+
| ``wontfix``       | Labelers may apply    |                       |
|                   | this label to issues  |                       |
|                   | that clearly have     |                       |
|                   | nothing at all to do  |                       |
|                   | with the project or   |                       |
|                   | are otherwise         |                       |
|                   | entirely out          |                       |
+-------------------+-----------------------+-----------------------+

.. _feature requests: #request-a-feature
.. _Committers: #join-the-project-team
.. _PR review process: #review-pull-requests

Review Pull Requests
--------------------

While anyone can comment on a PR, add feedback, etc, PRs are only
*approved* by team members with Issue Tracker or higher permissions.

PR reviews use `GitHub's own review feature`_, which manages comments,
approval, and review iteration.

Some notes:

-  You may ask for minor changes ("nitpicks"), but consider whether they
   are really blockers to merging: try to err on the side of "approve,
   with comments".
-  *ALL PULL REQUESTS* should be covered by a test: either by a
   previously-failing test, an existing test that covers the entire
   functionality of the submitted code, or new tests to verify any
   new/changed behavior. All tests must also pass and follow established
   conventions. Test coverage should not drop, unless the specific case
   is considered reasonable by maintainers.
-  Please make sure you're familiar with the code or documentation being
   updated, unless it's a minor change (spellchecking, minor formatting,
   etc). You may @mention another project member who you think is better
   suited for the review, but still provide a non-approving review of
   your own.
-  Be extra kind: people who submit code/doc contributions are putting
   themselves in a pretty vulnerable position, and have put time and
   care into what they've done (even if that's not obvious to you!) --
   always respond with respect, be understanding, but don't feel like
   you need to sacrifice your standards for their sake, either. Just
   don't be a jerk about it?

.. _GitHub's own review feature: https://help.github.com/articles/about-pull-request-reviews/

Merge Pull Requests
-------------------

`Needs Collaborator`_: Committer

TBD - need to hash out a bit more of this process.

Tag A Release
-------------

`Needs Collaborator`_: Committer

TBD - need to hash out a bit more of this process. The most important
bit here is probably that all tests must pass, and tags must use
`semver`_.

Join the Project Team
---------------------

Ways to Join
~~~~~~~~~~~~

There are many ways to contribute! Most of them don't require any
official status unless otherwise noted. That said, there's a couple of
positions that grant special repository abilities, and this section
describes how they're granted and what they do.

All of the below positions are granted based on the project team's
needs, as well as their consensus opinion about whether they would like
to work with the person and think that they would fit well into that
position. The process is relatively informal, and it's likely that
people who express interest in participating can just be granted the
permissions they'd like.

.. _Needs Collaborator: #join-the-project-team
.. _semver: https://semver.org

You can spot a collaborator on the repo by looking for the
``[Collaborator]`` or ``[Member]`` tags next to their names.

If you are not yet part of the Organization on Github, send me your username and which team you want to be part of, backend or frontend, and you will be added as soon as possible.

Once you have joined the Organization team, you will be able to see the projects, where you will find a list with various tasks to perform. Also, you can go to the general documentation of the product where you will find a more detailed explanation of each task.
