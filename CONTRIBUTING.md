# Contributing to Intelli Trip Planner

:+1::tada: First off, thanks for taking the time to contribute! :tada::+1:

---

## Table of contents

- [How can I contribute?](#How-can-I-contribute?)
  - [Reporting bugs](#Reporting-bugs)
  - [Suggesting features and enhancements](#Suggesting-features-and-enhancements)
  - [Submitting pull requests](#Submitting-pull-requests)
- [How do I get started?](#How-do-I-get-started?)
  - [Initial setup](#Initial-setup)
  - [Workflow](#Workflow)
  - [Bring your fork up to date with the original repository](#Bring-your-fork-up-to-date-with-the-original-repository)
  - [Other useful commands](#Other-useful-commands)
- [Styleguides](#Styleguides)
  - [Git commit messages](#Git-commit-messages)
  - [Python styleguide](#Python-styleguide)
- [Other recommended practices](#Other-recommended-practices)
  - [Sign commits with signature verifications](#Sign-commits-with-signature-verifications)

---

## How can I contribute?

### Reporting bugs

In the bug report, please follow these steps:

- Use a clear and descriptive title for the issue to identify the problem.
- Describe the exact steps which reproduce the bug.
- Describe the behavior you **_observed_** and point out what exactly is the problem with that behavior.
- Explain the behavior you **_expected_** to see instead and why.
- Include screenshots, animated GIFs or videos to demostrate the bug.
- Describe the environment in which the bug is observed, including the operating system, the Python version and the browser you are using (if applicable).

### Suggesting features and enhancements

In the feature or enhancement request, please follow these steps:

- Use a clear and descriptive title for the issue to identify the suggestion.
- Describe the current behavior and explain which behavior you expected to see instead and why.
- Explain why this enhancement would be useful.
- It's encouraged to use screenshots or drawings to demonstrate your point, if it helps.

### Submitting pull requests

Please follow these steps:

- Complete the [initial setup](#Initial-setup)
- Follow the [workflow](#Workflow)
- Follow the [styleguides](#Styleguides)

---

## How do I get started?

### Initial setup

- Prerequisites: having [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git), [Python 3.8.x](https://www.python.org/downloads/), [Poetry](https://python-poetry.org/docs/), [Node.js 12.x](https://nodejs.org/en/) and [Yarn](https://classic.yarnpkg.com/en/docs/install/) installed on your machine.
- Fork the repository. ([How to fork a repository?](https://help.github.com/en/github/getting-started-with-github/fork-a-repo#fork-an-example-repository))
- Clone this repository. ([How to clone a repository?](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository))
- In the terminal, change directory to the repository's root directory.
- Add the original repository as a remote called `upstream`:
  - To add the original repository as `upstream`, run command:
    ```
    git remote add upstream https://github.com/BadwaterBay/intelli-trip-planner.git
    ```
  - To verify you have added the original repository, run command:
    ```
    git remote -v
    ```
  - You should see the following output (assuming you are using HTTPS):\
    ```
    origin  https://github.com:<yourGitHubUsername>/intelli-trip-planner.git (fetch)
    origin  https://github.com:<yourGitHubUsername>/intelli-trip-planner.git (push)
    upstream  https://github.com/BadwaterBay/intelli-trip-planner.git (fetch)
    upstream  https://github.com/BadwaterBay/intelli-trip-planner.git (push)
    ```
- Install all dependencies with the following command. This could take a while.
  ```
  yarn --frozen-lockfile
  poetry install
  ```
- Run the server for development on your machine with command:
  ```
  yarn start
  ```
  By default, the server is hosted on [http://127.0.0.1:5000/](http://127.0.0.1:5000/).
- Visit [http://127.0.0.1:5000/](http://127.0.0.1:5000/) in your browser to confirm the server is running.
- To stop the server, press "Ctrl + C".

---

## Workflow

Our workflow is:

- Find an [issue](https://github.com/BadwaterBay/intelli-trip-planner/issues) you'd like to solve and claim it by leaving a comment.
- Complete the [initial setup](#Initial-setup), if you haven't.
- [Bring your fork up to date with the original repository](#Bring-your-fork-up-to-date-with-the-original-repository).
- Modify the code to solve the issue and commit changes.
- Make sure your base is up to date with the original repository (`upstream`) with commands:
  ```
  git fetch upstream
  git rebase upstream/master
  ```
- Push your commit to the remote of your forked repository. ([How to push commits to remote?](https://help.github.com/en/github/using-git/pushing-commits-to-a-remote-repository))
- Submit a pull request (PR) to be merged into the original repository's `master` branch. ([How to create a PR?](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request))
- Peers will review your PR and may request revisions.
- Once your PR is approved, your commit will be merged to the `master` branch. Congratulations!

If you are new to this workflow, you can a practice run here: [https://github.com/firstcontributions/first-contributions](https://github.com/firstcontributions/first-contributions)

If you are stuck, you are welcome to reach out and leave a comment.

---

## Bring your fork up to date with the original repository

- Completed the [initial setup](#Initial-setup), if you haven't.
- Fetch updates from the original repository (`upstream`):
  ```
  git fetch upstream
  ```
- Make sure you are on your local `master` branch:
  ```
  git checkout master
  ```
- Rebase your local `master` branch with `upstream/master` branch:
  ```
  git rebase upstream/master
  ```
- Push your local `master` to remote:
  ```
  git push origin master
  ```
  If your push is rejected ([why?](https://www.reddit.com/r/git/comments/6jzogp/why_am_i_force_pushing_after_a_rebase/)), you might need to force-push to remote:
  ```
  git push -f origin master
  ```

---

## Other useful commands

- Format your code using Prettier:
  - `yarn format` will format files with Prettier and save changes.
  - Tip: when you git-commit, `yarn format` will be automatically triggrred.
- Lint your code using Eslint:
  - `yarn lint` will run Eslint to check the code quality. Please try to resolve these issues before commiting any changes.
  - Tip: when you git-commit, `yarn lint` will be automatically triggrred.
- Create a production build:
  - `yarn build` will generate a production build of the Express app in directory `/dist-server`.
- Run tests:
  - `yarn test` will run preset tests. However, this is a dummy for now, because we haven't written any tests yet. This is to show that we are aware of the importance of unit testing.
- If you run into problems with Python dependencies:
  - Check if you are running Python 3.8.x in your local environment
  - Try `poetry install` to see if it solves your problems.
- If you run into problems with Node dependencies:
  - Try `yarn --frozen-lockfile` to see if it solves your problems.
  - If not, run `yarn refresh` to remove all dependencies in the `node_modules` directory and do a clean install of dependencies.

---

## Styleguides

### Git commit messages

- Use the present tense ("Add feature" not "Added feature").
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...").
- Limit the first line to 70 characters or less.
- Reference issues and pull requests liberally after the first line.
- When only changing documentation, include `[ci skip]` in the commit title.
- Consider starting the commit message with an applicable emoji:
  - :art: `:art:` when improving the format/structure of the code
  - :racehorse: `:racehorse:` when improving performance
  - :memo: `:memo:` when writing docs
  - :bug: `:bug:` when fixing a bug
  - :fire: `:fire:` when removing code or files
  - :green_heart: `:green_heart:` when fixing the CI build
  - :white_check_mark: `:white_check_mark:` when adding tests
  - :lock: `:lock:` when dealing with security
  - :arrow_up: `:arrow_up:` when upgrading dependencies
  - :arrow_down: `:arrow_down:` when downgrading dependencies
  - :shirt: `:shirt:` when removing linter warnings

### Python styleguide

We follow the [PEP 8 style guide](https://www.python.org/dev/peps/pep-0008/) and the [Black code style](https://github.com/psf/black/blob/master/docs/the_black_code_style.md). The [Black code style](https://github.com/psf/black/blob/master/docs/the_black_code_style.md) can be viewed as a strict subset of [PEP 8 style guide](https://www.python.org/dev/peps/pep-0008/).

---

## Other recommended practices

### Sign commits with signature verifications

It is encouraged to sign your commits with signature verifications with GPG keys. [How?](https://help.github.com/en/github/authenticating-to-github/managing-commit-signature-verification)