# Github Actions Bash Wrapper

Bash wrapper to capture the stdout and stderr output as `stdouterr`

## Usage

```
jobs:
  run:
    runs-on: ubuntu-latest
    defaults:
      run:
        shell: gha-bash-wrapper {0}
    steps:
    - name: Setup Github Actions Bash Wrapper
      uses: lmbbox/gha-bash-wrapper@v1
    - name: Run command
      id: cmd
      run: echo "Capture my output"
    - name: Create comment
      uses: peter-evans/create-or-update-comment@v4
      with:
        issue-number: ${{ github.event.pull_request.number }}
        body: ${{ steps.cmd.outputs.stdouterr }}
```
