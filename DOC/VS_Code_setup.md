# Use VS code for daily work


## Install plugins:

- `GitHub Pull Requests` 
  - https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github

Login with this extension into the enterprise github.

## Use options

Use following flags in your VS Code `Settings`:

- VS Code main window -> `File` -> `Preferences` -> `Settings`
- `Ctrl` + `,`
- `vscode://settings`

In `Settings` go to the section named:

- or copy setting ID like: `git.autofetch` into `Search Settings` input field (not the global `Search`!)

Settings to use:

### Git

#### Autofetch

- Change to "true"
- "git.autofetch": "true"

#### branchPrefix

- Add a prefix with your username.
- "git.branchPrefix": "/u/USERNAME/"

#### branchValidationRegex

> Optionally: we can decide what regex should looks like.

- "git.branchValidationRegex": ""

#### branchWhitespaceChar

- Check if there is: -
- "git.branchWhitespaceChar": "-"

#### pruneOnFetch

- Checkbox activate
- "git.pruneOnFetch": true


#### pullBeforeCheckout

- Checkbox activate
- "git.pullBeforeCheckout": false

#### showUncommitted

- Checkbox activate
- "git.timeline.showUncommitted": true

### GitHub Enterprise


#### github-enterprise.uri

- Add enterprise URL

### Github Pull Requests


### allowFetch

- Checkbox activate
- "githubPullRequests.allowFetch": true

### Create Default Base Branch

- Allow VS Code to set into branch for you
- "githubPullRequests.createDefaultBaseBranch": "createdFromBranch"

### Default Create Option

- VS Code can create PR as draft by default.
- "githubPullRequests.defaultCreateOption": "createDraft"

### Default Merge Method

- VS Code will choose the default merge method for you. Use "squash"!
- "githubPullRequests.defaultMergeMethod": "squash"

### Post Create

- VS Code will checout the default branch for you after PR creation.
- "githubPullRequests.postCreate": "checkoutDefaultBranchAndShow"