---
title: "「鯖缶工場」で務めて分かった、Mastodonを選ぶメリット"
date: 2018-12-17T09:39:40+09:00
thumbnail: "images/merit-of-choosing-mastodon-by-working-for-sabakan-industries/a3c3be8b6516327453173d7658c98484.png"
tags: [ "mastodon", "distributed_sns" ]
draft: false
toc: true
---

こちらの記事は[Mastodon Advent Calendar 2018](https://qiita.com/advent-calendar/2018/mastodon) 18日目の記事です。国見小道のブログにようこそおいでくださいました。17日目は[valerauko](https://pawoo.net/@valerauko)さんの [**分散型SNSの可視化**](https://blog.valerauko.net/2018/12/16/bunsan-gata-sns-no-kashika/) という記事でした。すげー人がpawooに潜んでいましたね。

さて、この記事で話したいことは **"「鯖缶工場」で務めて分かった、Mastodonを選ぶメリット"** です。なぜMastodonなのか？そのメリットを紹介しますが、のちに懸念点についても挙げておきます。よいFediverseを。

## 鯖缶工場とは

たびたびこのブログで話題にしております[**「鯖缶工場」**](https://wiki.sabakan.industries/)とは、有志による分散SNSサーバー立て支援コミュニティです。分散SNSサーバーのお手伝いだけでなく構築におけるノウハウの蓄積やトラブルシューティングなども行っています。[**創立者によるアドベントカレンダー記事を読みましょう。**](https://blog.drdr.work/2018/12/15/advent-calendar-2018-mastodon/)

僕もこのコミュニティに参加し、[しそのはさん](https://angraecumnote.net/@nantai_yuto)、[らっとさん](https://mstdn.rabbitodon.work/@rat)のMastodonサーバー立てのお手伝いをしました。自分が色々調べて回ってウオリャとサーバーを立てるのと、支援志願者の「わからないポイント」を対話を経て教えつつサーバーを立てるのは、違った種類の難しさがありました。また、教えることを通じて自分の知識が深まりました。皆さんもぜひ支援者になって回していきましょう。ここ最近は年末だからか支援志願者がおらんですけれども。

それでは、なぜMastodonなのか書いていきたいと思います。

## ドキュメントの充実

各分散SNSで**ドキュメントが最も充実しているのはMastodon**です。これは今のところ揺るぎません。サーバー運営者向けドキュメントを列挙しましょう。

- [GNU Social Documentation](https://git.gnu.io/gnu/gnu-social/blob/master/README.md)
  -> [akionux-wiki GNU socialのインストール](http://ja.akionux.net/wiki/index.php/GNU_social%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB) こっちのほうが丁寧で詳しいかも
- [Mastodon Documentation](https://docs.joinmastodon.org/)
- [Pleroma Documentation](https://git.pleroma.social/pleroma/pleroma/blob/develop/README.md)
- [Misskey Dokumentation](https://joinmisskey.github.io/ja/wiki/developers/)
- [microblog.pub Documentation](https://github.com/tsileo/microblog.pub/blob/master/README.md)

差は歴然ですね。

量が多いから充実しているというわけではありませんが、Mastodon以外のドキュメントが素っ気ないです。Misskeyは結構頑張ってる。GNUはwikiのほうが強い。

## 日本語話者のサーバー管理人の多さ

### 日本でのブレイクによる影響

2017年4月下旬に日本でMastodonが大ブレイクしたわけですが、そこから多くのサーバー管理者が誕生しました。v1.x.xで死んでるインスタンスも多いですが、その過程で凄腕の管理者が生まれ、その技術が脈々と口伝されている感じがあります。

日本サーバーについてはMastodonが群を抜いて多数、2位にMisskeyが来ているイメージです。海外に人気なのはPleromaでしょうか。

GNU Socialがどれほど活発なのかについては僕のほうからは確認できませんが、おひとりさま運営をしている方は何人かFediverseでお会いしています。歴史も長いほうなので資料は割と多く残されているのかも。

microblog.pubは僕が期待しているソフトウェアですが、利用者は製作者約1名しか知りません。3か月くらい前に「ドキュメントがっ役に立たない、俺がドキュメントだ」といったアノニマストがいた気がします。

### 戦争は数だよ兄貴

単純に「サーバー立てた人が多い」というのはオススメするのに強く影響しますね。触った人が多ければ多いほど、アドバイスが飛んでくる確率が上がります。「誰もが立て方を知ってるよ！」となったら、分散SNS時代が本格的に始まるといえそうです。・・・3年かかって実現できればいいほうだな。

### 大人数収容可能システム

mastodon.social, mstdn.jp, pawoo.netなどを見てみればわかる通り、Masotodonはインフラをチューニングすれば大人数を収容可能なシステムになっています。コミュニティ運営者としても立ち振る舞うものとしては、大人数が収容可能であることをわかっているのであれば安心して使える面もあると思います。

## 只者でない管理人たち

やべーやつらばかりです。鯖缶工場に行けばすぐ出会えます。ただ、これは懸念点にも上がりますが、**Mastodon使いに偏っています。**

ただ、基本的にはインフラが組めればサービスも乗っけられると思うので、ほかの分散SNSを建てるのにもそこまで大きな苦労はないんじゃないかと思います。... よね？

## 管理画面の扱いやすさ

サーバー管理者がモデレーターとしても動くことは多くあると思いますが、その際に注目するところは「アカウントに対しての操作がやりやすいかどうか」だと思います。**Mastodonはかなり丁寧に作りこまれています。**

ただこれはあくまで僕視点なので、ほかの分散SNSを立てた人が熱烈に「うちの管理画面すごいよぉ！」って宣伝してくれるのを待機してます。

### コマンドによる管理も豊富

Mastodonには`tootctl` という独自のコマンドが用意されており、[動作は多岐にわたります。](https://wiki.sabakan.industries/mastodon/tootctl) データベースやストレージを直接いじるような必要がないと明確にわかるのはいいですね。

## 本家の活発な開発体制

Mastodonでの開発速度はとても速いと思います。しばらく先までメンテナンスが行き届く環境になっていると思います。各分散SNSの開発体制については[墓場人夜さん](https://3.distsn.org/users/1)の [**「プラグイン機構は活発な開発者のかわりにはならない」**](https://hakabahitoyo.wordpress.com/2018/11/23/active-committer-is-better-than-plugin/) という記事に詳しく書かれております。...そういやHubzillaはどんな感じなんやろ。



---



さて、いろいろとメリットを挙げていきましたが、**ここからは懸念点を2つほどあげます。**

## 他分散SNS管理者の支援不足

**鯖缶工場では明らかにMastodon使いに偏っています。**[Fediverse.Network](https://fediverse.network/)を見てもわかるように、サーバーがどれくらいの割合で立てられているのかという比率においても同様の偏りがあると思います。Mastodonのサーバーが "Up" になっているのは2,552インスタンス、2番目に位置するPleromaは388インスタンス。**1位と2位の間ですでに6倍ほどの差が出ています。**

なので、ぜひMasotodon以外のサーバーを立てることにチャレンジしていただきたいなと思うのですが、分散SNSって運用あってこそなのでなかなかお願いするのもつらい感じがありますね。う～ん。

## ソフトウェア開発者の不足

さきほどの墓場さんの記事にもあるように、実はMastodonほどの開発者数でさえIssueの消化がおっついてない事案があります。他分散SNSについても、開発者不足は顕著です。GNU Social, microblog.pubについてはスナネコの懸念さえあります。

なので、サーバーを立てて分散SNSコミュニティを広めていくのも良いのですが、肝心のソフトウェアのメンテナンスも推し進めていかなければ、持続力がなくなってしまいます。サーバーを立てるのもいいですが、開発のほうにも力を入れてみましょうという次第です。

ところで、フォロワーからActivityPubを喋るサービスを新しく実験運用しているのを目にしております。個人的にとても楽しみにしております。

## おわりに

記事を書いていくにつれて、Mastodonの手厚さについて理解が深まりました。他の分散SNSも盛り上がっていけば、いつか分散SNSこそがSNSのスタンダードとなるかもしれません。僕としてはそんな未来を熱望しています。

次のアドベントカレンダー担当者は、[いつもの匠さん](https://mstdn.jp/@itsumotakumi)による「MastodonとAlexa的ななにか」です。いつもの匠さんも長くMastodonをやっている方ですね！楽しみです。