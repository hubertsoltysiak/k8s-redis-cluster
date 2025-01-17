# Contributing to k8s-redis-cluster

- [Opening New Issues](#opening-new-issues)
- [Code Style](#code-style)
- [Submitting Pull Requests](#submitting-pull-requests)
- [Configuring Github fork](#configuring-github-fork)

# Opening New Issues

Please log bugs or suggestions as [GitHub issues](https://github.com/pmem/k8s-redis-cluster/issues).
Details such as OS and other components version are always appreciated.

# Code Style

* Indent with tabs (width: 8)
* Max 90 chars per line

**NOTE**: We're not using specific format tool yet - feel free to propose your favourite.

# Submitting Pull Requests

We take outside code contributions to `k8s-redis-cluster` through GitHub pull requests.

**NOTE: If you do decide to implement code changes and contribute them,
please make sure you agree your contribution can be made available under the
[BSD-style License used for k8s-redis-cluster](LICENSE).**

**NOTE: Submitting your changes also means that you certify the following:**

```
Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

In case of any doubt, the gatekeeper may ask you to certify the above in writing,
i.e. via email or by including a `Signed-off-by:` line at the bottom
of your commit comments.

To improve tracking of who is the author of the contribution, we kindly ask you
to use your real name (not an alias) when committing your changes to k8s-redis-cluster:
```
Author: Random J Developer <random@developer.example.org>
```

# Configuring Github fork

To build and submit documentation as an automatically generated pull request,
the repository has to be properly configured.

* [Personal access token](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token) for Github account has to be generated.
  * Such personal access token has to be set in k8s-redis-cluster repository's
  [secrets](https://docs.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets)
  as `DOC_UPDATE_GITHUB_TOKEN` variable.

* `DOC_UPDATE_BOT_NAME` secret variable has to be set. In most cases it will be
  the same as Github account name.

* `DOC_REPO_OWNER` secret variable has to be set. Name of the Github account,
  which will be target to make an automatic pull request with documentation.
  In most cases it will be the same as Github account name.

To enable automatic images pushing to Github Container Registry, following variables:

* `CONTAINER_REG` existing environment variable (defined in workflow files, in .github/ directory)
  has to be updated to contain proper GitHub Container Registry address (to forking user's container registry),

* `GH_CR_USER` secret variable has to be set up - an account (with proper permissions) to publish
  images to the Container Registry (tab **Packages** in your GH profile/organization).

* `GH_CR_PAT` secret variable also has to be set up - Personal Access Token
  (with only read & write packages permissions), to be generated as described
  [here](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/creating-a-personal-access-token#creating-a-token)
  for selected account (user defined in above variable).
