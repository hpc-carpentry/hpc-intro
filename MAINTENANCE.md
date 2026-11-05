---
title: "Site Structure and Maintenance"
---

This site depends strongly on GitHub infrastructure, and a number of
operational decisions have been made during the development process
that may not be obvious to a casual or new contributor.

These are described below.

## Communications

### GitHub

The HPC Carpentry [GitHub organisation][project-github] contains the source repositories for all HPC Carpentry lessons.
Each of these lesson projects has its own team of maintainers and administrators.
The HPC Carpentry organisation also includes several other repositories related to the project.

In particular, there is a "coordination" [repo][coord-repo], which is
a good scope for issues and concerns for the HPC carpentry community
at large, rather than any particular lesson.

There is also a [repo][mainsite-repo] for the main website covering
all HPC-Carpentry activities. This is intended to be the "front door"
of the HPC Carpentry community.

### Slack

The main Carpentries Slack channel is reachable at
[carpentries.slack.com][swc-slack]. To become a member, you can
trigger in invitation from [the slack invitation link][slack-invite].

You can go directly to the HPC Carpentry sub-channel at
[#hpc-carpentry][hpc-slack]. These are the things to bookmark &mdash;
once you go there, the Slack engine redirects you to particular views,
so copying and pasting URLs out of the browser's location bar is
likely to be disappointing.

Members of existing swcarpentry Slack channels can find the channel by
typing "hpc-carpentry" into the Slack search box.

### E-mail

The top-level site is on The Carpentries' [Topicbox][topicbox]. There
are two HPC-specific lists, "discuss-hpc" and "maintainers-hpc". These
mailing lists are public: you may join any that catch your interest.
The system does not use passwords; log-ins are via a verification code
sent to your e-mail.

## Site Operation

### DOIs for Releases

There is a web-hook that calls out to [Zenodo][zenodo] to create a
Digital Object Identifier (DOI) whenever a release is generated on the
GitHub repo. The Zenodo account is owned by Peter Steinbach (@psteinb).

### Continuous Integration

The high-level lesson structure is described reasonably well in the
[README](README.md) file, but there are some subtleties that can arise
at build-time.

You can locally preview some of the tests by providing arguments to
the `make` command that you run in the top-level directory. In
particular, `make lesson-check-all` checks a number of important
things, like the existence of files with appropriate metadata. The
actual checks are executed by the Python script in
`bin/lesson_check.py`, which can be examined for important clues.

You can control what sorts of checks a file will be subject to by
selecting a `checker` type in the list of regular-expression matches
assigned to `CHECKERS` near the bottom of `bin/lesson_check.py`.

<!-- Reference -->

[hpc-intro]: https://github.com/hpc-carpentry/hpc-intro
[project-github]: https://github.com/hpc-carpentry
[coord-repo]: https://github.com/hpc-carpentry/coordination
[mainsite-repo]: https://github.com/hpc-carpentry/hpc-carpentry.org
[swc-slack]: https://carpentries.slack.com
[hpc-slack]: https://carpentries.slack.com/#hpc-carpentry
[slack-invite]: https://slack-invite.carpentries.org
[topicbox]: https://carpentries.topicbox.com
[zenodo]: https://zenodo.org/
