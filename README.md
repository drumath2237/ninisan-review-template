# ninisan Re:VIEW Template

![re:view](https://img.shields.io/badge/Re%3AVIEW-5.8-orange)
[![Build Book](https://github.com/drumath2237/ninisan-review-template/actions/workflows/build.yml/badge.svg)](https://github.com/drumath2237/ninisan-review-template/actions/workflows/build.yml)

## About

[にー兄さん](https://twitter.com/ninisan_drumath)作の Re:VIEW テンプレートです。
TechBooster 様の[TechBooster/ReVIEW-Template](https://github.com/TechBooster/ReVIEW-Template)を参考に、textlint のセットアップや docker-compose 対応などをしています（本 README の最後にクレジット表記あり）。

## Environment

- docker / docker-compose
- Re:VIEW 5.8
- yarn
- (Ruby 3.1)
- VSCode
- textlint

## Setup & Usage

textlint のインストールのために、`yarn install`コマンドを実行します（執筆中のみ必要）。
本のビルドは docker-compose によって行います。

```sh
# install npm dependency
yarn install

# open in vscode
code .

# build a book
docker compose up
```

### GitHub Actions の設定

mian ブランチへの push をトリガーすると本をビルドして結果を Discord へ通知するジョブが組まれています。
Discord チャンネルへ通知するためには`DISCORD_WEBHOOK`という名前で Webhook の URL をシークレットに登録してください。

## Licenses

- GitHub Actions, vscode の設定ファイル, docker-compose などの設定ファイルは MIT ライセンスです。再配布などの際には MIT ライセンスの定める範囲での権利者表記などをお願いします。
- articles/sty にあるファイルには以下のライセンスが適用されています。
  - review-jsbook.cls, review-base.sty, review-style.sty, review-custom.sty: MIT License
  - jumoline.sty: The LaTeX Project Public License
  - plistings.sty: MIT License
  - gentombow.sty: BSD License
  - jsbook.cls: BSD License
- その他ファイル群の権利は MIT ライセンスにて Techbooster 様に帰属します。

## Author

[にー兄さん](https://twitter.com/ninisan_drumath)
