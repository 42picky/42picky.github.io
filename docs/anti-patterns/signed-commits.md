---
tags:
  - hostile-architecture
  - github
  - anti-patterns
---

# Requiring signed commits

While using [signed git commits][1] is a good idea for a software
engineer, I also think that enforcing them on an open-source project is a
bad one too. Configuring commit signing is not a trivial task and it even
becomes more complex if you count the other ways people might attempt to
contribute to your project:

- Creating a pull-request from a secondary machine where you do not have
  all your GPG or SSH keys configured.
- Creating a pull-request from GitHub's web interface, which is very common
  for one-line fixes.
- Creating a pull request from service account, like github actions or
  applications.
- Any application that is fixing trivial mistakes in incoming pull-requests,
  like [pre-commit.ci][1] will likely produce unsigned commits too.

For these reasons, if you want to promote signed commits,
you should **only produce a warning message**, but not report a job failure on
CI pipelines if the commits are not signed.


[1]: https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits
