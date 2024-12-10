# nodejs-workflows
GitHub Action NodeJS workflows

## Reusable workflows

| Name                                                                                                                        | Description                      |
|-----------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| [gh-pages-publish.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/gh-pages-publish.yaml) | Publish API docs to GitHub Pages |
| [gh-release.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/gh-release.yaml)             | Create a GitHub Release          |
| [npm-publish.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/npm-publish.yaml)           | Publish an artifact on NPM       |
| [unit-ci.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/unit-ci.yaml)                   | Build and run Unit tests         |

## How to use
This project uses it's own workflows in order to test them (the NodeJS App/Lib is just a demo/example).  Copy and paste one or more of the following files into your project `.github/workflows` directory and update parameters accordingly:

| Name                                                                                            | Description                                             |
|-------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| [ci.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/ci.yaml) | Continuous Integration of an App/Lib                    |
| [cd.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/cd.yaml) | Continuous Deployment of an App/Lib with GitHub release |

The `ci` workflow invokes `unit-ci` to configure, build, and unit test.   The `ci` workflow can be customized with docker commands to launch containers and run integration tests ([Java Example](https://github.com/JeffersonLab/myquery/blob/e47681393f9a7a900dc1f0a932b6271bfa6356ed/.github/workflows/ci.yml#L20-L44])).

The `cd` workflow invokes `gh-release` and optionally `gh-pages-publish`.  The `gh-release` workflow uses the VERSION file to determine which tag to create.  The `cd` workflow generally should monitor the VERSION file for changes to trigger the workflow.

## Workflow Updates
Workflows are versioned in semver just as with regular software, however, the GitHub Action workflows convention is to reference a major version number such that backwards compatible minor and patch updates are received automatically.  This means a separate major tag such as `v1` must be moved after each release.  To move a major tag after a release execute (`v1` shown):

```
git tag -f v1
git push --tags -f
```

## See Also
- [Other workflows](https://github.com/search?q=org%3Ajeffersonlab+topic%3Agh-action-workflow&type=repositories)
- [Projects using this](https://github.com/search?q=org%3Ajeffersonlab+topic%3Anodejs-workflows&type=repositories)
