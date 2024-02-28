# Branching model

## Getting started

In this project we are using [Scaled Trunk-Based Development](https://trunkbaseddevelopment.com/#scaled-trunk-based-development).

## Branches

- `master` or `main` is a main branch and it is primarily used for production (release). It MUST be deployable at any time.
- Each team or individual will use their own fork of the repository with a feature branch and then create a PR to the development branch of the main repository. The convention for branch
naming is preferably `username/my-feature`, with few words as a branch name (keep it short and somewhat feature describing).
- Pull requests from feature branches should be pointing to a branch other than `master` or `main` (either a `development` branch or a hotfix branch). They are used for implementing all the changes to the codebase.
- The `development` branch is regularly merged to `master` or `main` branch, after the code and application has been tested (e.g.: after a sprint or a feature-focus).
- `release-v*` branches are created from the `master` or `main` branch and after succesful deployment/publish/test are merged back to master with increased version.
- Releases are done automatically via github actions on pushing a tag from a `release-v*` branch. Release branch has the same version in its' name as the product version that is being released with a tag created with yarn for different version changes (minor, major or patch) `yarn version --minor / -- major / --patch`

## Workflow example

1. Make sure your development branch is at the same tip as base repo origin version (you can use github to sync the fork)
2. Feature branch is created from `development` branch on users fork: `myUserName/new-select-ui`
3. Once developed and tested (including automation testing and going through the changes), feature branch is merged via **Pull Request** to its' development base branch.
4. Once `development` branch is stable and ready to release, it is merged to `master` or `main` the team member responsible for the release (maintainer) will create a `release-v` branch from `master` or `main` and push a new tag with `git push --follow-tags` and the CI github action will pick it up and create a release with artifacts.
5. After the active release branch is tested and all the CI checks pass, it can be merged  back to the `master` branch (with a new version).