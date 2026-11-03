<!--
Copyright (c) 2021 Dell Inc., or its subsidiaries. All Rights Reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# How to Contribute

Become one of the contributors to this project! We thrive to build a welcoming
and open community for anyone who wants to use the project or contribute to it.
There are just a few small guidelines you need to follow. To help us create a
safe and positive community experience for all, we require all participants to
adhere to the [Code of Conduct](CODE_OF_CONDUCT.md).

## Table of Contents

* [Become a contributor](#become-a-contributor)
* [Submitting issues](#submitting-issues)
* [Your first contribution](#your-first-contribution)
* [Signing your commits](#signing-your-commits)
* [Pull requests](#pull-requests)

## Become a contributor

You can contribute to this project in several ways. Here are some examples:

* Contribute to the CSD configuration and documentation.
* Report and triage bugs.
* Create feature requests.
* Fix bugs and implement features.
* Write technical documentation and blog posts, for users and contributors.
* Help others by answering questions about this project.

## Submitting issues

All issues related to the PowerScale CSD should be submitted
[here](https://github.com/dell/powerscale-csd/issues). Issues will be triaged
and labels will be used to indicate the type of issue.

### Report bugs

We aim to track and document everything related to the PowerScale CSD via the
Issues page. The code and documentation are released with no warranties or SLAs
and are intended to be supported through a community driven process.

Before submitting a new issue, make sure someone hasn't already reported the
problem. Look through the
[existing issues](https://github.com/dell/powerscale-csd/issues) for similar
issues.

When opening a Bug please include the following information to help with
debugging:

1. Version of relevant software: PowerScale CSD version, Cloudera Manager
   version, OneFS version.
2. Details of the issue explaining the problem: what, when, where.
3. The expected outcome that was not met (if any).
4. Supporting troubleshooting information.

An Issue __must__ be created before submitting any pull request. Any pull
request that is created should be linked to an Issue.

### Feature request

If you have an idea of how to improve this project, submit a feature request
via the Issues page.

## Your first contribution

Unsure where to begin contributing? Start by browsing issues labeled
`beginner friendly` or `help wanted`.

## Signing your commits

We require that developers sign off their commits to certify that they have
permission to contribute the code in a pull request. This way of certifying is
commonly known as the
[Developer Certificate of Origin (DCO)](https://developercertificate.org/).
We encourage all contributors to read the DCO text before signing a commit and
making contributions.

GitHub will prevent a pull request from being merged if there are any unsigned
commits.

### Signing a commit

GPG (GNU Privacy Guard) will be used to sign commits. Follow the instructions
[here](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/signing-commits)
to create a GPG key and configure your GitHub account to use that key.

Once Git and your GitHub account have been properly configured, you can add the
-S flag to the git commits:

```console
$ git commit -S -m your commit message
# Creates a signed commit
```

## Pull Requests

If this is your first time contributing to an open-source project on GitHub,
make sure you read about
[Creating a pull request](https://help.github.com/en/articles/creating-a-pull-request).

A pull request must always link to at least one GitHub issue. If that is not the
case, create a GitHub issue and link it.

To increase the chance of having your pull request accepted, make sure your pull
request follows these guidelines:

* Title and description matches the implementation.
* The pull request closes one related issue.
* The pull request contains necessary tests that verify the intended behavior.
* If your pull request has conflicts, rebase your branch onto the main branch.
