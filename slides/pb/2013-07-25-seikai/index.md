正解はひとつ！じゃない！！
==========

<address>[@tsucchi](http://twitter.com/tsucchi)</address>


自己紹介
---
+ 土田　拓也(つちだ　たくや)
+ [@tsucchi](http://twitter.com/tsucchi) とか [blog(http://tsucchi.github.io/)](http://tsucchi.github.io/)とか
+ 2013年6月より、[株式会社シャノン](http://www.shanon.co.jp/) という所で、Perl とか SQL とか書いてます
  + [技術ブログやってます！](http://shanon-tech.blogspot.jp/)


で、今回のテーマについて
---
+ 「Perl の文化」ですよね！

Perl の文化と言ったら...
---

これしかないだろう！
---

There's More Than One Way To Do It(TMTOWTDI)
---

日本語で言うと...
---

正解はひとつ！じゃない！！
---
<img src="./seikai.jpg" />


すいません、うそです
---

正解はひとつ！じゃない！！
---
+ 日本語では`「やり方はひとつじゃない」`とか`「やり方はいろいろある」`とか訳される事が多いです
+ ミルキィホームズめっちゃ好きなんです！
+ なので、個人的に`「正解はひとつ！じゃない！！」`を訳語として推したい！


で、それってどういう事？
---
+ 同じ事を実現するのに、やり方が一つじゃ無くてもいいよね！って事。
+ 簡単な例だと if と unless とか

```perl
if ( !defined $toys ) {
    print "トイズが無いのでダメダメですー";
}

unless ( defined $toys ) {
    print "トイズが無いのでダメダメですー";
}

```

+ どちらを使っても意味、というか動作は一緒

正解はひとつ！じゃない！！
---
+ Perl は構文から使い方に至るまで、こういうのがとても多い
+ 構文
 + if/unless
 + for/foreach
 + say/print/printf
 + or と ||
 + カンマ(,)とファットカンマ(=>)
+ 使い方
 + モジュール使う/使わない
 + オブジェクトどうする？
 + DB アクセスどうする？
 + Web アプリ作るのに、何使う？
+ etc.

構文について、もう少し
---
+ 色んな書き方があるのは多分悪い事じゃない。
 + 書き方が一つしかないと、それが気に入らない時、窮屈に感じますよね
 + さっきの if と unless はどっちでもいい

構文について、もう少し
---
+ でも、そうじゃないものもある

```perl
# 悪い例1) これは気持ち悪い。for を使うべき
foreach ( my $i=0; $i < @detective_names; $i++ ) {
    print "探偵さんの名前は$detective_names[$i]です¥n";
}

# 悪い例2) unless に複数の条件がくると読みにくい。
# if( !$is_police && !$has_toys ) (警察じゃなくてトイズが無い)の方が良い
unless ( $is_police || $has_toys ) {
    # 警察かトイズを持ってるでは無い？？？
    print "ダメダメ探偵かもしれません¥n";
}
```

「でも、ビギナーだし、そんなの分かんないよ！」
---

<img src="./beginner.jpg" width="60%" height="60%">

※ ビギナー(画像はイメージです)


「でも、ビギナーだし、そんなの分かんないよ！」
---
+ おっしゃる通りです
+ 分からないのはしょうがない。でも勉強しましょう！

「でも、ビギナーだし、そんなの分かんないよ！」
---
+ [perl - 現代的な Perl を再習得する方法は(http://blog.livedoor.jp/dankogai/archives/51222971.html)](http://blog.livedoor.jp/dankogai/archives/51222971.html)

```
一番大事なのは、役立つPerlプログラムを書くのに、Perlの全てを知っている必要は全くないということです。
小さなところから先に習ってよいのです。
Perlで赤ちゃん言葉を話しても、私たちは笑ったりしないと約束します。
```

+ 慣れないうちは、「赤ちゃん言葉」でもいいけど、いつまでも「赤ちゃん言葉」なのは恥ずかしいですよね！


「でも、どうやって勉強したら良いか、分からないよ！」
---

<img src="./study.jpg">

※画像はイメージです


「でも、どうやって勉強したら良いか、分からないよ！」
---
+ おっしゃる通りです。僕も結構苦労したし、今も苦労してます！
+ 本を読むのが一番効果的だと思う
+ 書き方なら「Perl ベストプラクティス」とか
  + こういう分厚い本だと、一人で読むのはちょっと辛いかも
  + 読書会とかいいかもしれない


<img src="./pbp.jpg" width="20%" height="20%">

「でも、どうやって勉強したら良いか、分からないよ！」
---
+ Perl Beginners のビギナーセッションで聞いてみる！
+ blog 書いてみると、コメントもらえるかも


使い方について、もう少し(1)
---
+ オブジェクトどうする？
  + 組み込みの方法 (bless)
  + Class::Accessor::*
  + Moose/Mouse/Moo みたいな高度なオブジェクトシステム使う

使い方について、もう少し(2)
---
+ DB アクセスどうする？
  + DBI でがんばる
  + O/R mapper(ORM)使う
      + DBIx::Class(DBIC)みたいな大規模なやつ使う
      + Teng みたいな軽いの使う

使い方について、もう少し(3)
---
+ Web アプリ
  + CGI?
     + さすがにもう無いかな？
 + Web Application Framework 使う
     + Catalyst みたいなフルスタック使う
     + Mojolicious とか Amon2 みたいな軽量なやつ使う

使い方について、もう少し(4)
---
+ こういうのは、流行り廃りがあるので、本当に難しい
  + 3年くらい前に主流だったのが、あっという間にオワコンになってしまったり...


「書き方覚えるのに精一杯で、流行りとか無理ですー」
---

<img src="./muridesu.jpg">

※無理ですー(画像はイメージです)


「書き方覚えるのに精一杯で、流行りとか無理ですー」
---
+ ですねー。でも、流行りがあるのは仕方ないです
  + アクティブに開発されている証拠ですからね！
  + Perl に限らず、どの言語使っていてもある

「書き方覚えるのに精一杯で、流行りとか無理ですー」
---
+ モジュールの選び方
  + [CPANソムリエになる方法 - http://blog.64p.org/entry/20080520/1211292598](http://blog.64p.org/entry/20080520/1211292598)

「書き方覚えるのに精一杯で、流行りとか無理ですー」
---
+ 大物(フルスタック)と小物(軽量級)
  + フルスタックの方が、できる事は多いし、大抵良くできてるけど、覚えるのが大変
  + 小物は制限があったりするけど、学習が楽で、何かあったときに追いかけるのも楽
  + 日本の Perl 使いは、小物を好む傾向が強い気がします


「書き方覚えるのに精一杯で、流行りとか無理ですー」
---
+ 雑誌読んでみるとか
+ blog 書いてみるとか
+ 各種チャットで聞いてみる、とか？
  + [Perl の話題を日本語で - http://lingr.com/room/perl_jp/](http://lingr.com/room/perl_jp/)
  + [Perl 入学式 - http://yancha.topolog.info/](http://yancha.topolog.info/)
  + [Hachioji.pm - http://yancha.hachiojipm.org:3000/](http://yancha.hachiojipm.org:3000/)

まとめ
---
+ TMTOWTDI = 正解はひとつ！じゃない！！
  + でも、いいやり方、悪いやり方はあるから、ちゃんと勉強しよう！
  + 分からないことは、聞いてみたり、blog 書いてみるといいと思う！

<img src="./mondaikaiketsu.jpg" width="50%" height="50%">

※ 問☆題☆解☆決☆(画像はイメージです)


おしまい
---

の、前に...
---

One More Thing
---

ふたりはミルキィホームズ 絶賛放送中！
---
+ http://milky-holmes-anime.com/futari/onair/
+ TOKYO MX 毎週土曜日　22:00～
+ BS日テレ  毎週日曜日　26:00～


<img src="./futariha_milky.jpg" width="40%" height="40%">

今度こそ おしまい
===