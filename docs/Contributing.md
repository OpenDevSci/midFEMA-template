# Welcome to midFEMA contributing guide <!-- omit in toc -->


----

### :hammer_and_wrench: Pull requests
A [pull request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) is a way to suggest changes in our repository. When we merge those changes, they should be deployed to the live site within 24 hours. :earth_africa:

* Collecting, addressing, and tracking feedback and contributions through **issues and pull requests**.

### Pull Request

When you're finished with the changes, create a pull request, also known as a PR.
- Fill the "Ready for review" template so that we can review your PR. This template helps reviewers understand your changes as well as the purpose of your pull request.
- Don't forget to [link PR to issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue) if you are solving one.
- Enable the checkbox to [allow maintainer edits](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/allowing-changes-to-a-pull-request-branch-created-from-a-fork) so the branch can be updated for a merge.
Once you submit your PR, a Docs team member will review your proposal. We may ask questions or request additional information.
- We may ask for changes to be made before a PR can be merged, either using [suggested changes](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/incorporating-feedback-in-your-pull-request) or pull request comments. You can apply suggested changes directly through the UI. You can make any other changes in your fork, then commit them to your branch.
- As you update your PR and apply changes, mark each conversation as [resolved](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request#resolving-conversations).
- If you run into any merge issues, checkout this [git tutorial](https://github.com/skills/resolve-merge-conflicts) to help you resolve merge conflicts and other issues.

----

# Contributing to `dbt-core`

1. [About this document](#about-this-document)
2. [Getting the code](#getting-the-code)
3. [Setting up an environment](#setting-up-an-environment)
4. [Running dbt-core in development](#running-dbt-core-in-development)
5. [Testing dbt-core](#testing)
6. [Debugging](#debugging)
7. [Adding or modifying a changelog entry](#adding-or-modifying-a-changelog-entry)
8. [Submitting a Pull Request](#submitting-a-pull-request)
9. [Troubleshooting Tips](#troubleshooting-tips)

## About this document

There are many ways to contribute to the ongoing development of `dbt-core`, such as by participating in discussions and issues. We encourage you to first read our higher-level document: ["Expectations for Open Source Contributors"](https://docs.getdbt.com/docs/contributing/oss-expectations).

The rest of this document serves as a more granular guide for contributing code changes to `dbt-core` (this repository). It is not intended as a guide for using `dbt-core`, and some pieces assume a level of familiarity with Python development (virtualenvs, `pip`, etc). Specific code snippets in this guide assume you are using macOS or Linux and are comfortable with the command line.

If you get stuck, we're happy to help! Drop us a line in the `#dbt-core-development` channel in the [dbt Community Slack](https://community.getdbt.com).

### Notes

- **Branches:** All pull requests from community contributors should target the `main` branch (default). If an issue fix applies to a release branch, that fix should be first committed to the development branch and then to the release branch (rarely release-branch fixes may not apply to `main`).
- **Releases**: Before releasing a new minor version of Core, we prepare a series of alphas and release candidates to allow users (especially employees of dbt Labs!) to test the new version in live environments. This is an important quality assurance step, as it exposes the new code to a wide variety of complicated deployments and can surface bugs before official release. Releases are accessible via pip, homebrew, and dbt Cloud.

## Getting the code

### Installing git

You will need `git` in order to download and modify the `dbt-core` source code. On macOS, the best way to download git is to just install [Xcode](https://developer.apple.com/support/xcode/).

### External contributors

If you are not a member of the `dbt-labs` GitHub organization, you can contribute to `dbt-core` by forking the `dbt-core` repository. For a detailed overview on forking, check out the [GitHub docs on forking](https://help.github.com/en/articles/fork-a-repo). In short, you will need to:

1. Fork the `dbt-core` repository
2. Clone your fork locally
3. Check out a new branch for your proposed changes
4. Push changes to your fork
5. Open a pull request against `dbt-labs/dbt-core` from your forked repository

### dbt Labs contributors

If you are a member of the `dbt-labs` GitHub organization, you will have push access to the `dbt-core` repo. Rather than forking `dbt-core` to make your changes, just clone the repository, check out a new branch, and push directly to that branch.

## Setting up an environment

There are some tools that will be helpful to you in developing locally. While this is the list relevant for `dbt-core` development, many of these tools are used commonly across open-source python projects.

### Tools

These are the tools used in `dbt-core` development and testing:

- [GitHub Actions](https://github.com/features/actions) for automating tests and checks, once a PR is pushed to the `dbt-core` repository


This will create and activate a new Python virtual environment.

#### Docker and `docker-compose`

Docker and `docker-compose` are both used in testing. Specific instructions for you OS can be found [here](https://docs.docker.com/get-docker/).


## Submitting a Pull Request
Code can be merged into the current development branch `main` by opening a pull request. If the proposal looks like it's on the right track, then a `dbt-core` maintainer will triage the PR and label it as `ready_for_review`. From this point, two code reviewers will be assigned with the aim of responding to any updates to the PR within about one week. They may suggest code revision for style or clarity, or request that you add unit or integration test(s). These are good things! We believe that, with a little bit of help, anyone can contribute high-quality code. Once merged, your contribution will be available for the next release of `dbt-core`.

Automated tests run via GitHub Actions. If you're a first-time contributor, all tests (including code checks and unit tests) will require a maintainer to approve. Changes in the `dbt-core` repository trigger integration tests against Postgres. dbt Labs also provides CI environments in which to test changes to other adapters, triggered by PRs in those adapters' repositories, as well as periodic maintenance checks of each adapter in concert with the latest `dbt-core` code changes.

Once all tests are passing and your PR has been approved, a `dbt-core` maintainer will merge your changes into the active development branch. And that's it! Happy developing :tada:

---

When contributing to this repository, please first discuss the change you wish to make via issue, email, or any other method with the owners of this repository before making a change.
{% if cookiecutter.include_code_of_conduct == 'y' -%}

## Development environment setup

> **[?]**
> Proceed to describe how to setup local development environment.
> e.g:

To set up a development environment, please follow these steps:

1. Clone the repo

   ```sh
   git clone https://github.com/{{cookiecutter.github_username}}/{{cookiecutter.repo_slug}}
   ```

2. TODO

## Issues and feature requests

You've found a bug in the source code, a mistake in the documentation or maybe you'd like a new feature?{% if cookiecutter.use_github_discussions == 'y' -%} Take a look at [GitHub Discussions](https://github.com/{{cookiecutter.github_username}}/{{cookiecutter.repo_slug}}/discussions) to see if it's already being discussed. {% endif %} You can help us by [submitting an issue on GitHub](https://github.com/{{cookiecutter.github_username}}/{{cookiecutter.repo_slug}}/issues). Before you create an issue, make sure to search the issue archive -- your issue may have already been addressed!

Please try to create bug reports that are:

- _Reproducible._ Include steps to reproduce the problem.
- _Specific._ Include as much detail as possible: which version, what environment, etc.
- _Unique._ Do not duplicate existing opened issues.
- _Scoped to a Single Bug._ One bug per report.

**Even better: Submit a pull request with a fix or new feature!**

### How to submit a Pull Request

1. Search our repository for open or closed
   [Pull Requests](https://github.com/{{cookiecutter.github_username}}/{{cookiecutter.repo_slug}}/pulls)
   that relate to your submission. You don't want to duplicate effort.
2. Fork the project
3. Create your feature branch (`git checkout -b feat/amazing_feature`)
4. Commit your changes (`git commit -m 'feat: add amazing_feature'`) {% if cookiecutter.use_conventional_commits == 'y' -%}
   {{cookiecutter.project_name}} uses [conventional commits](https://www.conventionalcommits.org), so please follow the specification in your commit messages.{% endif %}
5. Push to the branch (`git push origin feat/amazing_feature`)
6. [Open a Pull Request](https://github.com/{{cookiecutter.github_username}}/{{cookiecutter.repo_slug}}/compare?expand=1)


----

# Types of contributions :memo:
You can contribute to the GitHub Docs content and site in several ways. This repo is a place to discuss and collaborate on docs.github.com! Our small, but mighty :muscle: docs team is maintaining this repo; to preserve our bandwidth, off topic conversations will be closed.



### :mega: Discussions
Discussions are where we have conversations.

If you'd like help troubleshooting a docs PR you're working on, have a great new idea, or want to share something amazing you've learned in our docs, join us in [discussions](https://github.com/github/docs/discussions).

### :lady_beetle: Issues
[Issues](https://docs.github.com/en/github/managing-your-work-on-github/about-issues) are used to track tasks that contributors can help with. If an issue has a triage label, we haven't reviewed it yet, and you shouldn't begin work on it.

If you've found something in the content or the website that should be updated, search open issues to see if someone else has reported the same thing. If it's something new, open an issue using a [template](https://github.com/github/docs/issues/new/choose). We'll use the issue to have a conversation about the problem you want to fix.

### :hammer_and_wrench: Pull requests
A [pull request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) is a way to suggest changes in our repository. When we merge those changes, they should be deployed to the live site within 24 hours. :earth_africa:

We cannot accept contributions to the [REST API reference documentation](https://docs.github.com/en/rest/reference). If you spot an inaccuracy in the REST API reference documentation, open an issue in the [github/rest-api-description](https://github.com/github/rest-api-description/issues/new?template=schema-inaccuracy.md) repository.

### :question: Support
We are a small team working hard to keep up with the documentation demands of a continuously changing product. Unfortunately, we just can't help with support questions in this repository. If you are experiencing a problem with GitHub, unrelated to our documentation, please [contact GitHub Support directly](https://support.github.com/contact). Any issues, discussions, or pull requests opened here requesting support will be given information about how to contact GitHub Support, then closed and locked.

If you're having trouble with your GitHub account, contact [Support](https://support.github.com/contact?tags=docs-contributing-guide).



----

### To do list (to delete!)

- [ ] Fill in this document with more context and cleaner links
- [ ] Apply theme to final .rmd
- [x] Make GitHub Action that renders this document as html
- [ ] Include a little tutorial on a simple Github Action
- [ ] Set up a Github LFS workflow (*see section on this below... not sure about including this anymore*)
- [x] Set up an example for an issue and/or pull request prompt 

---

This Contributing Guide will walk you through how to contribute to this project. Contributions are always welcome, no matter how large or small.

Thank you for investing your time in contributing to our project! Any contribution you make will be reflected on [docs.github.com](https://docs.github.com/en) :sparkles:.

In this guide you will get an overview of the contribution workflow from opening an issue, creating a PR, reviewing, and merging the PR.

## New contributor guide

To get an overview of the project, read the [README](README.md) file. 


### Other Resources
Here are some resources to help you get started with open source contributions:

- [Finding ways to contribute to open source on GitHub](https://docs.github.com/en/get-started/exploring-projects-on-github/finding-ways-to-contribute-to-open-source-on-github)
- [Set up Git](https://docs.github.com/en/get-started/getting-started-with-git/set-up-git)
- [GitHub flow](https://docs.github.com/en/get-started/using-github/github-flow)
- [Collaborating with pull requests](https://docs.github.com/en/github/collaborating-with-pull-requests)


## Getting started

To navigate our codebase with confidence, see [the introduction to working in the docs repository](/contributing/README.md) :confetti_ball:. For more information on xxxxx, see "[xxxx](https://xxxxx).

## Features

## Content


---

# Contributions
<sup>[(Back to top)](#table-of-contents)</sup>

If this library helps you, you may want to consider
[buying the maintainer a cup of coffee](https://flattr.com/submit/auto?user_id=ivanperez-keera&url=https://github.com/ivanperez-keera/Yampa&title=Yampa&language=&tags=github&category=software).

## Discussions, issues and pull requests
<sup>[(Back to top)](#table-of-contents)</sup>

**Discussions**

If you have any comments, questions, ideas, or other topics that you think will
be of interest to the Yampa community, start a new discussion
[here](https://github.com/ivanperez-keera/Yampa/discussions). Examples include:

- You've created a new game or application that uses Yampa.
- You've written or found a library that helps use Yampa in a particular
  domain, or apply it to a specific platform.
- You've written or found a paper that mentions Yampa.
- You have an idea for an extension that will enable writing programs that are
  not currently possible or convenient to capture.
- You think you've found a bug.
- You want to propose an improvement (e.g., make the code faster or smaller).
- You have a question.
- Something in the documentation, a tutorial or a Yampa / FRP paper is unclear.
- You like the project and want to introduce yourself.

**Issues**

If a specific change is being proposed (either a new feature or a bug fix), you
can *open an issue* documenting the proposed change
[here](https://github.com/ivanperez-keera/Yampa/issues).

If you are unsure about whether your submission should be filed as an issue or
as a discussion, file it as a discussion. We can always move it later.

**Pull requests**

Once we determine that an issue will be addressed, we'll decide who does it and
when the change will be added to Yampa. Even if you implement the solution,
someone will walk you through the steps to ensure that your submission conforms
with our version control process, style guide, etc. More information on our
process is included below.

Please, do not just send a PR unless there is an issue for it and someone from
the Yampa team has confirmed that you should address it. The PR is *very*
likely to be rejected, and we really want to accept your contributions, so it
will make us very sad. Open a discussion / issue first and let us guide you
through the process.

---

<p align="center">
  <img src="https://raw.githubusercontent.com/dbt-labs/dbt-core/fa1ea14ddfb1d5ae319d5141844910dd53ab2834/etc/dbt-core.svg" alt="dbt logo" width="750"/>
</p>
<p align="center">
  <a href="https://github.com/dbt-labs/dbt-core/actions/workflows/main.yml">
    <img src="https://github.com/dbt-labs/dbt-core/actions/workflows/main.yml/badge.svg?event=push" alt="CI Badge"/>
  </a>
</p>

**[dbt](https://www.getdbt.com/)** enables data analysts and engineers to transform their data using the same practices that software engineers use to build applications.

![architecture](https://github.com/dbt-labs/dbt-core/blob/202cb7e51e218c7b29eb3b11ad058bd56b7739de/etc/dbt-transform.png)

## Understanding dbt

Analysts using dbt can transform their data by simply writing select statements, while dbt handles turning these statements into tables and views in a data warehouse.

These select statements, or "models", form a dbt project. Models frequently build on top of one another – dbt makes it easy to [manage relationships](https://docs.getdbt.com/docs/ref) between models, and [visualize these relationships](https://docs.getdbt.com/docs/documentation), as well as assure the quality of your transformations through [testing](https://docs.getdbt.com/docs/testing).

![dbt dag](https://raw.githubusercontent.com/dbt-labs/dbt-core/6c6649f9129d5d108aa3b0526f634cd8f3a9d1ed/etc/dbt-dag.png)

## Getting started

- [Install dbt](https://docs.getdbt.com/docs/get-started/installation)
- Read the [introduction](https://docs.getdbt.com/docs/introduction/) and [viewpoint](https://docs.getdbt.com/docs/about/viewpoint/)

## Join the dbt Community

- Be part of the conversation in the [dbt Community Slack](http://community.getdbt.com/)
- Read more on the [dbt Community Discourse](https://discourse.getdbt.com)

## Reporting bugs and contributing code

- Want to report a bug or request a feature? Let us know and open [an issue](https://github.com/dbt-labs/dbt-core/issues/new/choose)
- Want to help us build dbt? Check out the [Contributing Guide](https://github.com/dbt-labs/dbt-core/blob/HEAD/CONTRIBUTING.md)

If you get stuck, we're happy to help! Drop us a line in the #dbt-core-development channel in the dbt Community Slack.

----

# Contributions {#contributions}

Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

## Discussions, Issues and Pull Requests {#discussions-issues-and-pull-requests}

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

<p align="right">

(<a href="#readme-top">back to top</a>)

</p>

If you are interested in fixing issues and contributing directly to the code base, please see the document [How to Contribute](https://github.com/microsoft/vscode/wiki/How-to-Contribute), which covers the following:

-   [The development workflow](https://github.com/microsoft/vscode/wiki/How-to-Contribute#debugging)
-   [Submitting pull requests](https://github.com/microsoft/vscode/wiki/How-to-Contribute#pull-requests)
-   [Finding an issue to work on](https://github.com/microsoft/vscode/wiki/How-to-Contribute#where-to-contribute)

## Feedback

-   Connect on [Github Discussions](https://github.com/openresearchcollabs/midFEMA/discussions) or [Slack](https://join.slack.com/t/fiusunlab/shared_invite/zt-2c06cewsn-umIms6iXpnKa8NPwnsf_Xg)
-   [Request a new feature](/docs/Contributing.md)
-   [File an issue](https://github.com/microsoft/vscode/issues)
-   [Check the wiki](https://github.com/openresearchcollabs/midFEMA/wiki)


There are many ways in which you can participate in this project, for example:

* [Submit bugs and feature requests](https://github.com/microsoft/vscode/issues), and help us verify as they are checked in
* Review [source code changes](https://github.com/microsoft/vscode/pulls)
* Review the [documentation](https://github.com/microsoft/vscode-docs) and make pull requests for anything from typos to additional and new content

If you are interested in fixing issues and contributing directly to the code base,
please see the document [How to Contribute](https://github.com/microsoft/vscode/wiki/How-to-Contribute), which covers the following:

* [How to build and run from source](https://github.com/microsoft/vscode/wiki/How-to-Contribute)
* [The development workflow, including debugging and running tests](https://github.com/microsoft/vscode/wiki/How-to-Contribute#debugging)
* [Coding guidelines](https://github.com/microsoft/vscode/wiki/Coding-Guidelines)
* [Submitting pull requests](https://github.com/microsoft/vscode/wiki/How-to-Contribute#pull-requests)
* [Finding an issue to work on](https://github.com/microsoft/vscode/wiki/How-to-Contribute#where-to-contribute)
* [Contributing to translations](https://aka.ms/vscodeloc)

















 



















