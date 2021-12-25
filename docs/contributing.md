# Contributor Guide

This project is open-source under the [MIT license](https://opensource.org/licenses/MIT) and welcomes contributions
in the form of bug reports, feature requests, and pull requests.

Here is a list of important resources for contributors:

- [Source Code](https://github.com/militu/workstation-cli)
- [Documentation](https://militu.github.io/workstation-cli)
- [Issue Tracker](https://github.com/militu/workstation-cli/issues)

## How to report a bug

Report bugs on the [Issue Tracker](https://github.com/militu/workstation-cli/issues).

When filing an issue, make sure to answer these questions:

- Which operating system and Python version are you using?
- Which version of this project are you using?
- What did you do?
- What did you expect to see?
- What did you see instead?

The best way to get your bug fixed is to provide a test case, and/or
steps to reproduce the issue.

## How to request a feature

Request features on the [Issue Tracker](https://github.com/militu/workstation-cli/issues).

## How to set up your development environment

!!! note "Prefered method"

    Install the package and setup your workstation
    ```shell
    pip install workstation-cli --user
    workstation-install
    ```

If you don't want to setup your workstation with this package make sure to have Python 3.8+ and the following tools:

- [Poetry](https://python-poetry.org/)
- [Nox](https://nox.thea.codes/)
- [nox-poetry](https://nox-poetry.readthedocs.io/)

Fork the repository on [GitHub](https://github.com/militu/workstation-cli),
and clone the fork to your local machine.

```shell
pyenv install -s 3.8.12
pyenv local 3.8.12
poetry lock
nox -s pre-commit -- install
nox -s pre-commit -- install --hook-type commit-msg
```

## How to test the project

Please refer to the [User
Guide](https://cookiecutter-hypermodern-python.readthedocs.io/en/latest/guide.html#how-to-test-your-project)
for instructions on how to run the test suite locally.

## How to submit changes

Open a [pull request](https://github.com/militu/workstation-cli/pulls)
to submit changes to this project.

Your pull request needs to meet the following guidelines for acceptance:

- The Nox test suite must pass without errors and warnings.
- Include unit tests. This project maintains 100% code coverage.
- If your changes add functionality, update the documentation
  accordingly.

Feel free to submit early, though---we can always iterate on this.

It is recommended to open an issue before starting work on anything.
This will allow a chance to talk it over with the owners and validate
your approach.

## How to accept changes

_You need to be a project maintainer to accept changes._

Before accepting a pull request, go through the following checklist:

- The PR must pass all checks.
- The PR must have a descriptive title.
- The PR should be labelled with the kind of change.

To merge the pull request, follow these steps:

1.  Click **Squash and Merge**. (Select this option from the dropdown
    menu of the merge button, if it is not shown.)
2.  Click **Confirm squash and merge**.
3.  Click **Delete branch**.

## How to make a release

_You need to be a project maintainer to make a release._

Before making a release, go through the following checklist:

- All pull requests for the release have been merged.
- The default branch passes all checks.

Releases are made by publishing a GitHub Release. A draft release is
being maintained based on merged pull requests. To publish the release,
follow these steps:

1.  Click **Edit** next to the draft release.
2.  Enter a tag with the new version.
3.  Enter the release title, also the new version.
4.  Edit the release description, if required.
5.  Click **Publish Release**.

After publishing the release, the following automated steps are
triggered:

- The Git tag is applied to the repository.
