# actions-sver
GitHub Actions for sver

## install action
The install action is used to install **sver** and add it to the path for use in later GitHub Actions steps. To install the latest stable version, run:
```yaml
- uses: robzr/actions-sver/install
```
A specific version or version constraint can also be specified, in this example, the latest stable matching major version 1 would be installed:
```yaml
- uses: robzr/actions-sver/install
  with:
    version: v1, !pre
```
After the install action has been run, **sver** can be run like any other command available in the GitHub Actions runner:
```
- run: |
    # determine latest stable release
    echo -n 'The latest release is '
    git tag -l | sver max '!pre'
    
```