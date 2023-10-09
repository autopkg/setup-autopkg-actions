# setup-autopkg-actions

This is a shared github action for setting up AutoPkg to use within GitHub actions.

This allows a single place to keep the config required for getting AutoPkg running on MacOS / Windows / Linux runners, including self hosted runners.

## Simple Example:

```
      - name: setup-autopkg-actions step
        uses: autopkg/setup-autopkg-actions@v0.1.1
```

`v0.1.1` should be set to the newest release version of this repo when creating a new action.

Example action: https://github.com/jgstew/jgstew-recipes/blob/main/.github/workflows/Test_setup-autopkg-actions.yaml

## Full Example:

```
      - name: setup-autopkg-actions step
        uses: autopkg/setup-autopkg-actions@v0.1.1
        use-python-version: "3.11"
        use-autopkg-branch: dev
        set-powershell-policy: false
```
