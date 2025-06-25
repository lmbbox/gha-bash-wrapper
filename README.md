# Github Actions Bash Wrapper

Bash wrapper to capture the stdout and stderr output as `stdouterr`

## Usage

```
- name: Setup Github Actions Bash Wrapper
  uses: lmbbox/gha-bash-wrapper@main
- name: Run command
  id: cmd
  shell: gha-bash-wrapper
  run: echo "Capture my output"
```
