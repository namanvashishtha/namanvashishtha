# Save this as .github/workflows/snake.yml in your namanvashishtha/namanvashishtha repo
name: Generate snake animation

on:
  schedule:
    - cron: "0 0 * * *" # daily
  workflow_dispatch:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: namanvashishtha
          outputs: |
            dist/github-snake.svg?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9
            dist/github-snake-dark.svg?palette=github-dark&color_snake=purple

      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
