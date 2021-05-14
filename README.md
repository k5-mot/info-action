# info-action

## Features

GitHub Action for getting information of repository.

## Usage

### Output arguments

|Arguments |Contents             |Required|Sample            |
|:--:|:--:|:--:|:--:|
|owner     |Owner of Repository  |Optional|k5-mot            |
|repository|Name of Repository   |Optional|info-action       |
|version   |Version of Repository|Optional|v1.1.1            |
|version_hp|Version of Repository|Optional|v1-1-1            |
|version_ub|Version of Repository|Optional|v1_1_1            |
|release   |Name for Release     |Optional|info-action_v1_1_1|

## Example

```yaml:.github/workflows/ubuntu-test.yml
name: "ubuntu-test"

on:
  push:
    tags:
      - "v*"

jobs:
  test_job:
    runs-on: ubuntu-latest
    name: "demo"
    steps:
      - name: "Set up Git repository"
        uses: actions/checkout@v2

      - name: "info-action"
        id: info_action
        uses: k5-mot/info-action@main

      - name: "Print environment variables."
        run: |
          echo "OWNER      : ${{ steps.info_action.outputs.owner }}"
          echo "REPOSITORY : ${{ steps.info_action.outputs.repository }}"
          echo "VERSION    : ${{ steps.info_action.outputs.version }}"
          echo "VERSION_HP : ${{ steps.info_action.outputs.version_hp }}"
          echo "VERSION_UB : ${{ steps.info_action.outputs.version_ub }}"
          echo "RELEASE    : ${{ steps.info_action.outputs.release }}"
```

## References

* [Docker コンテナのアクションを作成する](https://docs.github.com/ja/actions/creating-actions/creating-a-docker-container-action)
* [GitHub Actionsのワークフローコマンド](https://docs.github.com/ja/actions/reference/workflow-commands-for-github-actions)
* [GitHub Actions のコンテキストおよび式の構文](https://docs.github.com/ja/actions/reference/context-and-expression-syntax-for-github-actions)
* [複合実行ステップ アクションの作成](https://docs.github.com/ja/actions/creating-actions/creating-a-composite-run-steps-action)
* [Docker Hub texlive/texlive](https://hub.docker.com/r/texlive/texlive/)

## Note

Good luck!!!

## Author

* k5-mot

## License

Copyright (c) 2021 k5-mot All Rights Reserved.

"k5-mot/latexmk-action" is under [MIT license](https://en.wikipedia.org/wiki/MIT_License).

