# Repo Linker GitHub Action

This GitHub Action automates the process of linking repositories by pulling content from a source repository and pushing it to a destination repository.

## Usage

### Inputs

#### `source-repo`

URL of the source repository to pull data from.

#### `source-repo-branch`

Branch name of the source repository from which data will be pulled.

#### `destination-repo`

URL of the destination repository to push data to.

#### `destination-repo-branch`

Branch name of the destination repository where data will be pushed.

#### `token`

Access token or personal access token (PAT) with repository access for authentication and pushing data.

#### `git-user-name`

GitHub username or the name to be associated with the commit when pushing to the destination repository.

#### `git-user-email`

Email of the GitHub user for commit attribution when pushing to the destination repository.

### Example Workflow

```yaml
name: Link Repositories

on:
  push:
    branches:
      - main # or your preferred branch

jobs:
  link-repos:
    runs-on: ubuntu-latest
    steps:
      - name: Link Repositories
        uses: RKeertishKumar/link-repos-action@main # replace with the actual repository and version
        with:
          source-repo: 'https://github.com/source-owner/source-repo'
          source-repo-branch: 'main'
          destination-repo: 'https://github.com/destination-owner/destination-repo'
          destination-repo-branch: 'main'
          token: ${{ secrets.ACCESS_TOKEN }}
          git-user-name: 'YourGitHubUsername'
          git-user-email: 'your.email@example.com'
