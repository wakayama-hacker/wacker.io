---
layout:     post
title:      "Wacker #7 Pepper ハック"
date:       2016-10-18
author:     "Takayuki Miyauchi"
header-img: "img/2016-10-18-pepper.jpg"
---

2016/10/16に開催されたWackerの第8回勉強会では、[和歌山県立情報交流センター Big-U](http://www.big-u.jp/)さんからソフトバンク社製のロボット「Pepper」をお借りして、Pepperのハックに挑戦しました。

<blockquote class="instagram-media" data-instgrm-captioned data-instgrm-version="7" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:658px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50.0% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAMUExURczMzPf399fX1+bm5mzY9AMAAADiSURBVDjLvZXbEsMgCES5/P8/t9FuRVCRmU73JWlzosgSIIZURCjo/ad+EQJJB4Hv8BFt+IDpQoCx1wjOSBFhh2XssxEIYn3ulI/6MNReE07UIWJEv8UEOWDS88LY97kqyTliJKKtuYBbruAyVh5wOHiXmpi5we58Ek028czwyuQdLKPG1Bkb4NnM+VeAnfHqn1k4+GPT6uGQcvu2h2OVuIf/gWUFyy8OWEpdyZSa3aVCqpVoVvzZZ2VTnn2wU8qzVjDDetO90GSy9mVLqtgYSy231MxrY6I2gGqjrTY0L8fxCxfCBbhWrsYYAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div> <p style=" margin:8px 0 0 0; padding:0 4px;"> <a href="https://www.instagram.com/p/BLnAgvWDift/" style=" color:#000; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none; word-wrap:break-word;" target="_blank">He can dance!</a></p> <p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;">A video posted by Takayuki Miyauchi (@miya0001) on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2016-10-16T03:56:26+00:00">Oct 15, 2016 at 8:56pm PDT</time></p></div></blockquote>
<script async defer src="//platform.instagram.com/en_US/embeds.js"></script>

## Pepperの取り扱いについて

* おでこに手をあてて、カメラを隠すとスリープする。なんだか笑けた。
* 液晶の裏にあるボタンが電源ボタン。動作中にこれを押すとステータス情報を話してくれる。

## 技術的な情報などなど

* PepperのOSは、[NAOqi](http://doc.aldebaran.com/)というOS。
* SSHでログインもできる。SSHのユーザー名は `nao` で、パスワードは初期設定時に設定するらしい。
* APIもあった。ウェブサーバーにはNginxが使われていた。
* このAPIを使用して動かしたり、しゃべらせたりすることができる。そしてこのAPIは認証もなにもない。。。大丈夫か？

## 参考

* [Pepper for Dev](http://www.softbank.jp/robot/special/tech/) - 本家の開発者向けポータル
* [Pepperめも ～ペッパーリモコン作ってみた～](http://qiita.com/haiattoC/items/a7390fdfecf697586fb3) - IPを指定しただけで本当に動いた。まじか。。。
* [vagrant-pepper-dev](https://github.com/wakayama-hacker/vagrant-pepper-dev) - Pepper SDK用のVagrant環境。NAISTの学生さんが作ってくれたものをフォークして `ansible_local` で動くようにしました。

## 感想

一番に思ったのは大丈夫か？ということ。同じネットワークに入れればやりたい放題なのね。。。

でもおかげでいろいろ探ることができました。もう一度機会があれば[Leap Motion](https://www.leapmotion.com/?lang=jp)と繋げたいです。

最後に会場及びPepperを提供してくださったBig-U様ありがとうございました。
