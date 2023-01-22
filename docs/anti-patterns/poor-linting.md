---
tags:
  - linting
---

# Poor linting

There should be no debate around the fact that any project that aims to accept
contributions from outside should have a linting pipelines setup. Still, the
devil is in the details on how this is implemented and in particular how easy is
to run the linting locally and get the same results as the CI pipeline.

## Each linter being called manually

If you expect that the contributor will have to call more than one command for
linting the project, you are already failed the [KISS](../../principles/kiss)
part.

If you need to document how to run the linters in more than a sentence, you
probably need to find a way to improve that. The need to document how to
contribute is a possible sign that maybe you did not make it easy enough.

## Linting stops at the first found error

It is not uncommon for projects to have more than a dozen linters configured and
if your current linting command stops at the first error, you are forcing the
user to run it multiple times without even knowing how much they have to work.

Tools like [pre-commit](https://pre-commit.com/) can help you to address this
because they can act as an orchestrator and they can report all errors at once.

## Not including isolation for the tools

If your local testing does not include containing the tools into a virtual
environment and controlling exactly their versioning, your users will struggle
to make use of them because their tools will behaver differently.

## Avoiding default configuration filenames

If you are not keeping the tool configuration files in their standard location,
other users will fail to load their configuration and have unexpected behavior.

If you end up ever having to pass the config file location to such a tool. Keep
in mind that user editors and IDEs will have plugins that run the same tools,
plugins that will fail to find your "custom" configuration file.

## Diverging from standard settings

While disabling some checks that you either do not agree with or you do not want
to bother with, is a perfectly valid reason, you should do your best to avoid
imposing your personal preferences.

A clear example here is the line length limit. Tools like [black][1] have a
default value of 88 characters, and you should not change this to any other
value.

> > If you value contributions, keep in mind that consistency between projects
> > is more important than your personal preferences.

The less you diverge from defaults, the easier it will be for others to
contribute to your project.

[1]:
  https://black.readthedocs.io/en/stable/the_black_code_style.html#line-length
