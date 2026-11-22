# github-workflows
Reusable GitHub Actions workflows for red-oxide (and chrisppy) repositories.

## check.yml

Runs `nix flake check`. Pass `cachix` to pull from a Cachix cache and push
builds to it on pushes to the default branch (pull requests only pull):

```yaml
jobs:
  check:
    uses: red-oxide/github-workflows/.github/workflows/check.yml@master
    with:
      cachix: red-oxide
    secrets: inherit
```

## update-flake-lock.yml

Runs `nix flake update` and commits the new `flake.lock`.

```yaml
jobs:
  update-flake-lock:
    uses: red-oxide/github-workflows/.github/workflows/update-flake-lock.yml@master
    permissions:
      contents: write
```
