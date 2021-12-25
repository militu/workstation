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

!!! note "Preferred method"

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

!!! warning "On first install"

    ```shell
    pyenv install -s 3.8.12
    pyenv local 3.8.12
    poetry lock
    nox -s pre-commit -- install
    nox -s pre-commit -- install --hook-type commit-msg
    ```

## How to run your code

First, install the project and its dependencies to the Poetry
environment:

```shell
poetry install
```

=== "Run interactive session"

    ```shell
    poetry run python
    ```

=== "Invoke command-line interface"

    ```shell
    poetry run workstation-install
    ```

## How to test the project

Run the test suite using `Nox`:

```console
$ nox -r
```

## How to submit changes

Create a branch for your changes:

```shell
git switch --create my-new-branch main
```

Create a series of small, single-purpose commits:

```shell
git add <files>
git commit
```

Push your branch to GitHub:

```shell
git push --set-upstream origin my-topic-branch
```

Open a [pull request](https://github.com/militu/workstation-cli/pulls)
to submit changes to this project.

1.  Select your branch from the _Branch_ menu.
2.  Click **New pull request**.
3.  Enter the title for the pull request.
4.  Enter a description for the pull request.
5.  Apply a `label`
6.  Click **Create pull request**.

Your pull request needs to meet the following guidelines for acceptance:

- The Nox test suite must pass without errors and warnings.
- Include unit tests. This project maintains 100% code coverage.
- If your changes add functionality, update the documentation
  accordingly.

Release notes are pre-filled with the titles of merged pull requests.

## How to accept a pull request

Before accepting a pull request, go through the following checklist:

- The PR must pass all checks.
- The PR must have a descriptive title.
- The PR should be labelled with the kind of change.

If all checks are marked as passed, merge the pull request using the
squash-merge strategy:

1.  Click **Squash and Merge**.
2.  Click **Confirm squash and merge**.
3.  Click **Delete branch**.

## How to make a release

Before making a release, go through the following checklist:

- All pull requests for the release have been merged.
- The default branch passes all checks.

Releases are triggered by a version bump on the default branch.
Do this in a separate pull request:

1. Switch to a branch.
2. Bump the version using the `release` session in `nox`.
3. Push to GitHub.
4. Open a pull request.
5. Merge the pull request.

The individual steps for bumping the version are:

```shell
git switch --create release main
nox -s release -- --patch
git push origin release
```

To let `semantic-release` decide what version number to update to, use:

```shell
nox -s release
```

Before merging the pull request for the release,
go through the following checklist:

- The pull request passes all checks.
- The development release on TestPyPI\_ looks good.
- All pull requests for the release have been merged.
