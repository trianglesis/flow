# Trunk

It can be `pre`, `dev`, `qa` or anything.

## Trunk origins and lifecycle

- The branch `trunk` is created from the `main`, once.
- Users should create personal branches from the `main`, but merge via **#PR** into the `trunk`.
- **#PR** into the `trunk` requires teammates approval only!

## Move changes from 'trunk' to 'main'

- Tests must pass in `trunk` 
  - user creates branch `from-trunk-to-main` based on the `main` branch.
  - user creates a **#PR** into the `main` by cherry-picking from the `trunk`.
  - system attaches test results to this **#PR** and external review can be initiated.
  - **#PR** from the `trunk` into the `main` requires core team or manager approvals.
- User "Squash and Merge" his **#PR** into the `main`.

## The main branch receiving merge commits from trunk

Everyhing is already tested in the `trunk` reviewed and approved.

- As soon as `main` is full of features we need to release now - create a `release` branch.
  - The `release` branch is now detached from the main.
  - The `release` branch can receive only hotfixes if build fails!
  - Release branch should be merged back to `main` if there were any hotfixes.

## The release is ready and finished:

- Create a `release` package in the repo based on the `release` branch and assign the tag: `0.0.1`
  - Use this tag point as a useful diff to compare releases and see the history.
  - the `main` branch rebases back into the `trunk`
    - The `main` branch may also include `hotfixes` from the release branch.


## Disaster:

- The branch `trunk` can be deleted and recreated if complications occur.
- We do not care if history of the `trunk` is inconsistent, but we should have `main` to be equal to `trunk` after each release!


# Drawing:


![alt text](pic/GitHubWork_ater_flow.png)