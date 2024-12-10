# nodejs-workflows
GitHub Action NodeJS workflows

| Name                                                                                                                        | Description                      |
|-----------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| [gh-pages-publish.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/gh-pages-publish.yaml) | Publish API docs to GitHub Pages |
| [gh-release.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/gh-release.yaml)             | Create a GitHub Release          |
| [npm-publish.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/npm-publish.yaml)           | Publish an artifact on NPM       |
| [unit-ci.yaml](https://github.com/JeffersonLab/nodejs-workflows/blob/main/.github/workflows/unit-ci.yaml)                   | Build and run Unit tests         |

## Workflow Updates
Workflows are versioned in semver just as with regular software, however, the GitHub Action workflows convention is to reference a major version number such that backwards compatible minor and patch updates are received automatically.  This means a separate major tag such as `v1` must be moved after each release.  To move a major tag after a release execute (`v1` shown):

```
git tag -f v1
git push --tags -f
```

## See Also
- [Other workflows](https://github.com/search?q=org%3Ajeffersonlab+topic%3Agh-action-workflow&type=repositories)
- [Projects using this](https://github.com/search?q=org%3Ajeffersonlab+topic%3Anodejs-workflows&type=repositories)
