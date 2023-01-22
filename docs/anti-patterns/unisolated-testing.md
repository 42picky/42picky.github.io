# Unisolated testing

A very common mistake developers make when configuring the testing for their
projects is to perform system or user wide reconfiguration, basically overriding
whatever the user running the test has configured.

While it is perfectly normal to have some system level requirements and even to
have a setup script that attempts to install them when missing, this **should
not happen without the user's consent**.

The same setup scripts can be run in unattended mode on CI/CD pipelines, but
when run on interactive mode, they should always prompt the user.

One of the most common isolation solutions is the use of virtual environments,
which exist for most programming languages.
