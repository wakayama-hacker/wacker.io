---
layout:     post
title:      "Wagrant という Web 系の勉強会用の Vagrant 環境を作りました。"
date:       2016-12-19
author:     "Takayuki Miyauchi"
header-img: "img/2016-12-19-wagrant.png"
---

Wacker では言語や技術を問わず、毎回いろいろなジャンルの勉強会を行っていますが、開発環境の構築に費やす時間がどうしてもそれなりに発生してしまうので、WEB 系の勉強会を想定した汎用的な Vagrant 環境をつくりました。

[https://github.com/wakayama-hacker/wagrant](https://github.com/wakayama-hacker/wagrant)

インストールされているものは以下のような感じです。

* Ubuntu 16.04 Xenial64
  * Apache
  * MySQL
  * PHP 7
  * Ruby 2.3
  * Node.js 6.x

## 特徴

たいした特徴はなにもありませんが（むしろそれを重視）、以下のようにあらかじめパスが通ってたりします。

```.bash_profile
export COMPOSER_HOME=$HOME/.composer
export PATH=$HOME/.composer/vendor/bin:$PATH
export PATH=$HOME/.npm-packages/bin:$PATH

if which ruby >/dev/null && which gem >/dev/null; then
  PATH="$(ruby -rubygems -e 'puts Gem.user_dir')/bin:$PATH"
fi
```

あと、`.gemrc` にあらかじめ `gem: --user-install` って書いてあったり、`.npmrc` に `prefix = ${HOME}/.npm-packages` と書いてあったりします。

## 使い方

1. [VirtualBox](https://www.virtualbox.org/) および [Vagrant](https://www.vagrantup.com/) をあらかじめインストールしてください。
2. [最新版](https://github.com/wakayama-hacker/wagrant/releases)を任意のディレクトリにダウンロードしてください。
3. ダウンロードしたファイルを任意のディレクトリに解凍してください。

つづけてコマンドラインで以下のように操作してください。

```
$ cd ~/Desktop/wagrant
$ vagrant up
```

`vagrant` についてはドキュメントをご覧になってください。

[https://www.vagrantup.com/docs/](https://www.vagrantup.com/docs/)

ハンズオンや勉強会で使用する際には、参加者にかならず `vagrant destroy` をしてもらいましょう。
