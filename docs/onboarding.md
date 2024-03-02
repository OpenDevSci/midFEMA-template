
Template from: https://github.com/greenelab/onboarding/blob/master/onboarding.md

onboarding.md

The repository is home to the onboarding information for the [midFEMA Project](https://github.com/openresearchcollabs/midFEMA).


Communication
General
Slack: We use slack for rapid communication within the lab. If you plan on sending an e-mail to someone within the lab, try a slack message instead. This helps to keep communications in one place, and xxx commits to respond to slacks (not necessarily immediately, but the same guarantee is not made for e-mail). There are many channels on our lab's slack; however, it is recommended that newcomers join the following channels: #general, #lab-meeting, #journalclub, #random, #wins.

Projects: when one lab member reports an issue on a project on GitHub, it would not be appropriate for another lab member to reply "I'll drop by your desk and show you how to solve that." It would be most appropriate for the conversation to take place on GitHub issues.

Version Control Services: Our primary version control service is GitHub, and we have a greenelab account there. We expect that lab members will maintain their code in repositories under these team accounts. However, lab member should not commit to the branch that is shown as default on GitHub for any of these repositories. Instead commits happen as described below to facilitate code review.

Creating a Greenelab Repository:

Create a repository under the team account.
Immediately fork this repository into one that your user account owns.
Make commits to your own repository, and move code back to the greenelab repository as described below.
Getting Code into Greenelab Repositories: Code moves from user repositories to greenelab repositories through a process of code review. Code review is handled through pull requests. The process is described briefly below. Feel free to ask for guidance if you are uncomfortable with the process. We will revoke write access for failing to adhere to these rules.

Make changes to your code and commit them in your own repository first.
Create a pull request into the repository owned by Greenelab.
Name potential reviewers for your pull request.
Once at least one lab member has approved your pull request, you or a reviewer may merge your pull request. The only exception to this policy is this repository ("onboarding") where, in addition to the above rules, Casey must also approve the pull request.

Composition of Pull Requests: Each pull request may contain one or more changesets. In keeping with good source control practice, each changeset or commit should contain all changes necessary for a particular fix or update. In addition, each pull request should relate to no more than one functional area in the code base you are updating. Keeping the pull request focused to one area makes it easier for your reviewers to provide thoughtful feedback.

Reviewing Pull Requests: We expect that all lab members will participate in review of pull requests. If you get named by the submitter, it's courteous to review the request. We have created a checklist to facilitate review. As a reviewer, you are responsible for making sure that all checklist guidelines are followed.

Projects that didn't work: We expect that repositories will contain failures (e.g. proof-of-concepts that didn't work). This is ideal. Being able to find them will make sure we don't make the same failure twice.

Non-Code Versioning: Non-code documents should be kept in a place that maintains version history. Penn provides Box for these purposes. The University of Colorado provides OneDrive for this purpose.

Data Management: For publicly available data, scripts used to download and process these data should be preserved, as should the versions of items used in processing (e.g. probe to gene mappings). These items should be version controlled. Where possible, intermediate files of reasonable size can be stored to facilitate re-use, but the process to regenerate these files from publicly available data should be preserved. When we generate data, they should be stored in a location where they are replicated and uploaded to the relevant database as soon as possible (e.g. GEO for gene expression, SRA for sequencing).

Reproducibility: We expect all lab members to maintain code that performs reproducible analyses. This can be in the form of makefiles, shell scripts, or other automation approaches that allow analyses to be automatically performed. We expect that these scripts, including those to generate figures in papers generated as a consequence of such analyses, will be included in source control repositories (see "Getting Code into Greenelab Repositories") and made publicly available before or concurrent with the submission of preprint (if submitted) or manuscripts. Combined with the review guidelines, this means that all code must have been reviewed for these documents to be submitted.

How to Modify this Document
This is a living document. The repository is at GitHub. To make changes, fork, edit the files you wish, and create a pull request. The pull request process is handled as described in the Getting Code into Greenelab Repositories section of coding_and_software.
