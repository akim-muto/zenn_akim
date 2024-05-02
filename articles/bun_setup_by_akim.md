---
title: "Bunのセットアップ"
emoji: "👌"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Javascript", "TypeScript", "Bun"]
published: true
---
# Bunのセットアップ
## 概要
この記事ではBunのセットアップについてまとめる。

Bunはオールインワンのランタイム&ツールキットだ。
この記事を執筆中の2024/5/2時点でバージョン1.1.6までリリースされている。

バージョンは１を超えていて、公式のblogでバージョン１の記事を公開した際に"Bun is stable and production-ready."と述べている。

軽く調べた感じだと規模の大きなプロダクションでの採用事例はうまく見つけられなかった。パブリックにアプリやサービスを公開していて、コードが見れるか、記事としてある程度実態を紹介してくれてる事例があったらコメントで教えてくれると嬉しい。

Bunそのものについてはこの辺の記事で。
https://zenn.dev/ak/articles/c21609fd3b0fdc

## Bunのインストール
英語ですけど、必要なコマンドは分かるはず。Linuxの場合はunzipパッケージが必要だよ！ということも書いてあります。
https://bun.sh/docs/installation

Bun自体のバージョン管理ツールは以下の奴を見つけたが、まだバージョン0.5で使って見た話も聞かないので、私はさわってない。リスクが理解できたうえで興味のある方はどうでしょう？
https://github.com/owenizedd/bum
## NpmとNode.jsのインストール
### そもそもインストールが必要か
前にローカルでとあるフレームワークをBunで動かしたときはNode.jsがないと動かなかった。

プロダクション環境でもランタイムにBunを使うなら、そもそもNode.jsと依存関係があるのはどうなんだという話になるが、開発環境だけでBunを使うなら、とりあえずインストールして動かすということもあると思う。

なのでNode.jsをいれずにBunだけで動かしてみて依存関係に問題があったらNode.jsのインストールを検討するということでもいいかも。

Node.jsがすでに入ってる環境を使ってる人の方が多そうだから。プロダクション環境でちょっと動かしてみたらNode.jsがなくて動かないなんてこともあるかな。
### インストール
nvmを使うのが推奨されてる。
https://learn.microsoft.com/ja-jp/windows/dev-environment/javascript/nodejs-on-windows#install-nvm-windows-nodejs-and-npm
https://github.com/coreybutler/nvm-windows
https://github.com/nvm-sh/nvm

シムリンクの関係で代替手段が必要な場合があるかもだけど、その辺はよく知らないのでこの記事では掘り下げない。いちおう直接インストールするためのインストーラーのリンクを貼っとく。
https://nodejs.org/en/download

## コマンド一覧
簡単な使い方として"Bun help"で出てくるコマンドをざっと紹介。
|コマンド|対象の指定サンプル|説明|
| ---- | ---- | ---- |
|run|./my-script.ts or lint|Bunでファイルを実行。またはpackage.jsonのscriptを実行|
|test||Bunでユニットテストを実行|
|x|prettier|package binaryの実行とオートインストール。ようはnpxのBunバージョン(bunx)|  
|repl||Bunでreplのセッションを開始|
|exec||Bunで直接Shellスクリプトを実行|
|install||package.jsonから依存関係をインストール(bun i)|
|add|svelte|package.jsonに依存関係を追加(bun a)|
|remove|@remix-run/dev|package.jsonから依存関係を消去(bun rm)|
|update|left-pad|外部依存関係をアップデート|
|link|[\<package>]|ローカルnpm packageを登録かリンク|
|unlink||ローカルnpm packageの登録を解除|
|pm|\<subcommand>|package management utilitiesを追加|
|build|./a.ts ./b.jsx|TypeScript & JavaScript をシングルファイルにバンドル|
|init||ブランクテンプレートから空のBunプロジェクトを開始|
|create|@evan/duckdb|テンプレートからBunプロジェクトを作成(bun c)|
|upgrade||Bunを最新バージョンにアップグレード|
|\<command> --help||コマンドのヘルプを参照|
## おわりに
Bunはまだまだ新しいプロダクトなので安定性には問題があるかもしれないが、できるだけBunを使っていきたいと思っている。