
# Index

## [NPM Publish Alpha](./npm-publish-alpha.yaml)

Publishing an alpha release version of a Node.js package to the NPM registry. Triggered when pushing to any branch excluding `main`. A custom alpha tag is created in the following format:
```
${CURRENT_VERSION}-alpha.${SANITISED_BRANCH_NAME}-dd-mm-yyyy-hhmmss
``` 
Where `CURRENT_VERSION` is the version listed in the `package.json` and `SANITISED_BRANCH_NAME` is the current branch name (sanitisation is applied to replace `/` with `-`) e.g. `1.2.3-alpha.001-patch-11-07-2025-104423`. 
An NPM access token must be generated and added as a GitHub repository secret with the name `NPM_ACCESS_TOKEN`.  

## [NPM Publish Stable](./npm-publish-stable.yaml)

Publishing a stable release version of a Node.js package to the NPM registry. Triggered when pushing or merging into `main`. Updates the latest version of the Node.js package on the NPM registry using the version declared in the `package.json`. An NPM access token must be generated and added as a GitHub repository secret with the name `NPM_ACCESS_TOKEN`.

## [PR Approval Bot](./pr-approval-bot.yaml)

Post a comment once a PR is approved.
