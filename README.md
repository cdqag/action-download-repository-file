# download-repository-file

Download a repository file from a given path.
Might be useful when you need to download a file from a repository in a GitHub Actions context, and you don't want to clone the whole repository.

## Dependencies:

`curl` and `jq` must be installed in the environment where this action is being used.

## Authentication

## Usage

```yaml

# Example usage with secrets.GITHUB_TOKEN
- name: Get myFile.txt from GitHub repository
  uses: cdqag/action-download-repository-file@v0.2.0
    with:
      organization: my-github-organization
      repository: my-github-repository-name
      file-path: some-directory/sub-directory/myFile.txt
      target-file: myFile.txt
      github-token: ${{ secrets.GITHUB_TOKEN }}

- name: Cat the downloaded file
  run: |
    cat myFile.txt
```

### Inputs

| Name                 | Description                          | Mandatory |
|----------------------|--------------------------------------|---------|
| `organization`            | GitHub organization | yes     |
| `repository`            | GitHub repository name| yes     |
| `file-path`            | Path to the file (relative to the repository root)| yes    |
| `target-file`            | Where to store the downloaded file contents| yes     |
| `github-token`            | GitHub token that will be used to download the file| yes     |

