# GitHub Actions
A collection of GitHub Actions.

## Contents
### [NPM Publish Alpha](./npm-publish-alpha.yml)
- Publishing an alpha release version of a Node.js package to the NPM registry. 
- This action is triggered when pushing to any branch excluding the `main` branch. 
- A custom alpha tag is created in the format of 
```
${CURRENT_VERSION}-alpha.${SANITISED_BRANCH_NAME}-dd-mm-yyyy-hhmmss
``` 
Where `CURRENT_VERSION` is the version listed in the `package.json` and `SANITISED_BRANCH_NAME` is the branch where current commits are being pushed (sanitisation is applied to replace `/` with `-`) e.g. `1.2.3-alpha.001-patch-11-07-2025-104423`. 
- The published package can be installed via either command:
```
npm i package@alpha
npm i package@1.2.3-alpha.001-patch-11-07-2025-104423
``` 
- An NPM access token must be generated and added as a GitHub repository secret with the name `NPM_ACCESS_TOKEN`.  

### [NPM Publish Stable](./npm-publish-stable.yml)
- Publishing a stable release version of a Node.js package to the NPM registry.
- This action is triggered when pushing or merging into the `main` branch.
- Updates the latest version of the Node.js package on the NPM registry using the version declared in the `package.json`.
- The published package can be installed via `npm i package` or `npm i package@latest`. 
- An NPM access token must be generated and added as a GitHub repository secret with the name `NPM_ACCESS_TOKEN`.