# Automate code formatting

Using linters that enforced code-style is a good practice for any project that
aims to have more than one person working on it. However, the way the maintainer
chooses to enforce code style does make a big difference, as this could easily
create a lot of friction for contributors.

Luckily, these days many tools can help with this and which can automatically
fix code style even on incoming pull requests.

One notable example is [pre-commit.ci](https://pre-commit.ci/) which you can
install as a GitHub App on your repository. This will automatically run and push
fixes on top of incoming pull requests. It will never push to your main branch.
Nobody should be able to push to your main branch if you configured your
repository correctly, including yourself.
