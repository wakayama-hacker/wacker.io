# Wacker Blog

http://wacker.io/

## 記事の書き方

`_posts` ディレクトリ以下に以下のフォーマットで記事を投稿してください。

### ファイル名

`2016-10-18-pepper-hack.md` のように日付、タイトルをハイフォンで区切ったファイル名としてください。

### 記事のフォーマット

以下のフォーマットを参考にしてください。

```
---
layout:     post
title:      "Wacker #7 Pepper ハック"
date:       2016-10-18
author:     "Takayuki Miyauchi"
header-img: "img/2016-10-18-pepper.jpg"
---

記事の本文はここから
```

## Jekyll環境の構築

まず、このブログを `git clone` してください。

```
$ git clone git@github.com:wakayama-hacker/wacker.io.git
```

この環境を構築するにはRuby及びBundlerが必要です。まだの場合はそれらをインストールしてください。

次に以下のコマンドでJekyll環境を構築します。

```
$ cd wacker.io
$ bundle install --path vendor/bundle
$ bundle exec jekyll serve
```

以上が完了したら [http://127.0.0.1:4000/](http://127.0.0.1:4000/) にアクセスしてください。
