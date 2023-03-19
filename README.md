# Shoten13 ASA Book

[![Build Re:VIEW Book](https://github.com/drumath2237/shoten14-deepdive-babylon-webxr-book/actions/workflows/build.yml/badge.svg)](https://github.com/drumath2237/shoten14-deepdive-babylon-webxr-book/actions/workflows/build.yml)
[![reviewdog](https://github.com/drumath2237/shoten14-deepdive-babylon-webxr-book/actions/workflows/textlint.yml/badge.svg)](https://github.com/drumath2237/shoten14-deepdive-babylon-webxr-book/actions/workflows/textlint.yml)

## About

書典 14 で頒布する技術同人誌のリポジトリ。
Babylon.js と WebXR に関する内容になる予定。

## Environment

- docker / docker-compose
- Re:VIEW 5.5
- yarn
- (Ruby 3.1)
- VSCode
- textlint

## Setup & Usage

yarn の install の際、Ruby の Gem も一緒にインストールする設定になっているため
Ruby 環境がないとエラーになることがあります。
ローカルで textlint を動かすだけであれば Ruby は必要ないので、
`package.json`の`scripts`にある`postinstall`というスクリプトを 1 行消してから`yarn install`してください。

```json :package.json
{
  ...
  "scripts": {
    "global-bundler": "gem install bundler",
    "global": "npm run global-bundler",
    "postinstall": "bundle install",      // <=========== ここ1行消す（終わったら戻す）
    "pdf": "grunt pdf",
	...
  },
  ...
}
```

textlint のインストールには、`yarn install`コマンドを実行します。

```bash
# install npm dependency
yarn install

# run vscode
code .
```

## Build

### docker-compose

docker compose が使える環境であれば、`docker compose up`コマンドでビルド可能です。

### ビルドスクリプト

docker compose が使えない場合、docker を用いてビルドします。

`./build.**`という形式のファイルは gitignore に設定しています。
Docker の起動スクリプトなどに使ってください。

下記は Windows バッチファイルの例です。

```bat
@echo off
@rem change mount directory name
@rem ex) D:\shoten12-webar-babylon-book
docker run -it --rm -v /d/shoten12-webar-babylon-book/:/book vvakame/review:5.5 /bin/bash -ci "cd /book/articles && review-pdfmaker config.yml"
```

