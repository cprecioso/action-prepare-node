# action-prepare-node

Installs Node.js, Corepack, Yarn, and install the dependencies. Uses a cache for
speeding up following runs.

## Project requirements

- Use a
  [`.node-version` file](https://github.com/shadowspawn/node-version-usage)
- Use yarn 2+

## Usage

Add the action to the job(s) in your workflow(s) where you need Node and your
dependencies available.

For example:

```yml
jobs:
  build:
    runs-on: ubuntu-latest

    permissions:
      contents: read
      packages: read

    steps:
      - uses: actions/checkout@v3
        with:
          persist-credentials: false
      - uses: cprecioso/action-prepare-node@v1
      - run: yarn build
```
