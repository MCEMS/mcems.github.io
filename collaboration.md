---
layout: markdown
---

# General Guidelines

* Use Slack or GitHub for all communication. This way, everyone will be kept in the loop. There's also a record of it that anyone can refer back to later.
* Debating the best strategy encouraged, but be civil and open to alternatives.
* When it comes to access, default to open. We trust each other not to intentionally (or unintentionally) mess things up. There may be situations in which access needs to be restricted, but let's not unnecessarily impede progress.

# GitHub Teams

* `www`: People who work on the public website. Probably includes the Technology Officer, maybe others.
* `core`: Developers who work on the backend and various apps.

# Workflow

We will use the [GitHub Flow](https://guides.github.com/introduction/flow/index.html) for a branching model. In short,

* `master` branch is always deployable
* Create "feature" branches directly off `master` and merge back into `master` through a Pull Request.
* Use pull requests for discussion

Before you merge a PR:

* All unit tests must be passing on Travis
* **Get someone else to look at your code.** A PR shouldn't be merged without any commentary. Conversely, if you see an open PR, have a quick look at what's being changed. Leave feedback, even if it's just a `:+1:` or `:shipit:` so that the author knows you've looked.
* If you're working on a Heroku project, have a look at the review app and make sure it looks okay. Unit test should take care of this, but you never know.

