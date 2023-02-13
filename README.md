# temp-devops-test

Added various bits of extra CI goodness.

## High level things to understand

Github deployments

Different levels of tests

Auto deploying and concurrency

Workflow logic

### PRs and the Dev environment

Any actions on an active PR (e.g. opening a PR on already-pushed code, or pushing any new code to an open PR, or reopening a closed PR) will automatically trigger deployments to the *DEV* environment, regardless of the test run status.

### Main branch and the Staging environment

Any pushes to the `main` branch will automatically trigger a deployment to the *STAGING* environment, but only if the full test suite passes on that commit

### Releases and the Production environment

Any Release will automatically trigger a deployment to the production branch, but only if the commit that the Release tag points to already has a fullt est suite passed on it
