# setup-autopkg-actions

This is a shared github action for setting up [AutoPkg](https://github.com/autopkg/autopkg) to use within GitHub actions.

This allows a single place to keep the config required for getting [AutoPkg](https://github.com/autopkg/autopkg) running on MacOS / Windows / Linux runners, including self hosted runners.

## Simple Example:

```
      - name: setup-autopkg-actions step
        uses: autopkg/setup-autopkg-actions@v0.1.2
```

`v0.1.2` should be set to the newest release version of this repo when creating a new action.

Example action: https://github.com/jgstew/jgstew-recipes/blob/main/.github/workflows/Test_setup-autopkg-actions.yaml

## Full Example:

```
      - name: setup-autopkg-actions step
        uses: autopkg/setup-autopkg-actions@v0.1.2
        with:
          use-python-version: "3.11"
          use-autopkg-branch: dev
          set-powershell-policy: false
```

Example action: https://github.com/jgstew/jgstew-recipes/blob/main/.github/workflows/Test_setup-autopkg-actions_full.yaml

## Usage:

After the github action step which sets up [AutoPkg](https://github.com/autopkg/autopkg), you can invoke it like the following: (Cross Platform)

```
      - name: run recipe autopkg
        run: python autopkg/Code/autopkg run -vv Test-Recipes/AutopkgCore.test.recipe.yaml
```

The AutoPkg repo will actually be cloned into the `./autopkg` folder relative to the current working directory and on the branch specified.

This means that you need to invoke autopkg itself by using `python autopkg/Code/autopkg command` where "command" is whatever command you wish to run. Using POSIX paths to invoke autopkg will work on all platforms including Windows.
