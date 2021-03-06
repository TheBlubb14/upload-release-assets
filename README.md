## Upload Release Assets - GitHub Action

<a href="https://github.com/AButler/upload-release-assets"><img alt="GitHub Actions status" src="https://github.com/AButler/upload-release-assets/workflows/CI/badge.svg"></a>

The Upload Release Assets GitHub Action uploads files (base on a glob) to a GitHub release. This is a cross-platform action that runs on any environment.

### Usage

```yml
jobs:
  build:
    # ...
    steps:
      - uses: AButler/upload-release-assets@v2.0
        with:
          files: 'artifacts/*;packages/*.nupkg'
          repo-token: ${{ secrets.GITHUB_TOKEN }}
```

### Inputs

| Name          | Description                                                                                       | Examples                                                 |
|---------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------|
| `files`       | The glob of files to upload (semicolon separate multiple globs)                                   | `file.txt` <br> `file*.txt` <br> `file_{a,b}.txt;*.json` |
| `repo-token`  | The GitHub token to use to amend the release _(recommended to use `${{ secrets.GITHUB_TOKEN }}`)_ | `${{ secrets.GITHUB_TOKEN }}`                            |
| `release-tag` | _(Optional)_ Specify the tag of the release to upload to                                          | `v1.0.0`                                                 |
