# surge.sh publish action

This action deploy your project with [surge.sh](https://surge.sh)

## Inputs

### `domain`

**Required** Domain set for your service.

### `project`

Path to your build project. Default: `.`

### `login`

**Required** Your user login

### `token`

**Required** Token obtained with `surge token` command

## Example usage

```yaml
name: My workflow

on: push

jobs:
  my-job:
    name: My job
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to foo-bar.surge.sh
        uses: dswistowski/surge-sh-action@v1
        with:
          domain: 'foo-bar.surge.sh'
          project: '.'
          login: ${{ secrets.surge_login }}
          token: ${{ secrets.surge_token }}
```
