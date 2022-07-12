# Isabelle Build GitHub Actions

Build an Isabelle theory file in github actions

## Example

To use this action, create a file called `.github/workflows/build.yml` in your repository, with the following contents:

TODO: Update the example below when the next tag is available

```
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    name: Build Theory
    steps:
      - uses: actions/checkout@v3
      - uses: lexbailey/isabelle-theory-build-github-action@main
        with:
          isabelle-version: '2021-1'
```

## Options

These are the values you can add in the "with" section of the build step in the build.yml file

 - `isabelle-version` Which version of isabelle to use to build. Currently only `2021-1` is recognised.
 - `depends` Whitespace-separated list of other things to build before building this. Format is `<clone_url>@<ref>`. The options for the build are picked up from any workflow yml files found in the dependency repo
 - `session-name` Session name to use with the `isabelle build -b 'session-name'` command. Leave blank to default to the name of the repo on github.
 - `theory-root` Path to the directory to be added under isabelle's `src` directory, the dir where your ROOT file is. Leave blank to default to the root of the repo.
