# test-github-artifacts
github artifacts を試してみる

https://docs.github.com/ja/actions/guides/storing-workflow-data-as-artifacts

## download
ブラウザからのダウンロード
https://docs.github.com/ja/actions/managing-workflow-runs/downloading-workflow-artifacts#

github cli を使ったダウンロード
```bash
# 引数の数字は run-id。ブラウザで実行ログを見たときのURLの最後の部分。
gh run download 970269987
```

### api で
https://docs.github.com/en/rest/reference/actions#artifacts
を見てゴニョゴニョすれば出来そう？

```bash
# get artifacts
curl \
  -H "Accept: application/vnd.github.v3+json" \
  https://api.github.com/repos/pa-k-sato/test-github-artifacts/actions/artifacts
 # download
curl \
  --dump-header - \
  -H "Accept: application/vnd.github.v3+json" \
  https://api.github.com/repos/pa-k-sato/test-github-artifacts/actions/artifacts/70344501/zip
```

download が `403`エラーとなる。。。

```json
{
  "message": "You must have the actions scope to download artifacts.",
  "documentation_url": "https://docs.github.com/rest/reference/actions#download-an-artifact"
}
```

## nuxt
アプリは nuxtjs を自動生成したもの
## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
