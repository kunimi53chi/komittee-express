---
title: "ブログ構築しました"
date: 2017-12-26T19:06:07+09:00
tags: [ "Hugo", "Netlify" ]
---

初投稿です。当ブログはHugo+Netlifyで作成しています。テーマは「[Robust](https://themes.gohugo.io/robust/)」です。

## 風呂でスマホいじりながら考えたブログタイトル

ブログタイトルは「Komittee Express」と名付けました。スピード感あふれる表現、みたいなイメージ。Expressっていう単語が面白く、結構気に入ってます。

## ブログ環境

- GitHub & Dropbox　（ソース・リポジトリ管理）
- Hugo （静的サイトジェネレータ）
- Netlify　（ホスティングサービス）
- GitBook　（ドキュメント変換　記事が長いときや説明書などに使う）

## "I did it !" List

1. WinにHugoインストール　[ここ](https://qiita.com/biotist/items/ea860ebfb1214aacaf43) と[ここ](http://devlog.work/archives/124) 参考
2. [Netlify導入](https://qiita.com/biotist/items/ea860ebfb1214aacaf43)
3. ためしにブログをローカルで立ち上げる
    - testsiteに移動して`hugo server -t something_theme -D -w`
4.  Netlify構築
    - [参考](https://blog.mismithportfolio.com/web/hugo-netlify-build)
    - ウォッチするリポジトリは`D:\Dropbox\Hugo\Sites\testsite`にした
    - ビルドコマンドは `hugo --theme=beautifulhugo --buildDrafts`
        - `--buildDrafts` いる？
        - `draft=true`の記事も公開するってことかな。ドラフト記事はまだ公開しない記事のこと。公開したいなら `false` にする。
    - Buildに失敗したので[これ見ながらやり直し](https://monaural.net/post/201707/set-hugo-version-on-netlify/)
    - Build & Deploy > Continuous Deployment > Build environment variables にて
        - `key=HUGO_VERSION value=0.31.1` に設定。これは `$ hugo env` でチェックした。  
5. [テストでのブログ公開が完了](https://testes-test-hugolify.netlify.com/)したので、本格的にブログ環境構築にのりだす。
6. Branch subdomainsというところから`Staging`環境を作れるということなので引き続きテストでやってみる
    - Netlify 1アカウントでステージング環境を作るのは無理ぽい？
        - [プルリクをプレビューすることができそう](https://www.netlify.com/blog/2016/07/20/introducing-deploy-previews-in-netlify/)。
7. HTTPS化を試みる。...というか自動作成してくれたアドレスがすでにSSL有効だった。Netlify神かよ。
8. さて本番リポジトリはどこをビルド起点にすればいいやら。テストと同じでいいのか調べる
9. Themeを[Tranquilpeak](https://themes.gohugo.io/hugo-tranquilpeak-theme/)に
    - うまくいかなかったので[Robust](https://themes.gohugo.io/robust/)に変更した
10. [ここ](http://blog.zzzmisa.com/customize_hugo_theme/)などを参考にしてプロフィールや更新日表示など追加した

## 本番環境構築ログ

```
// ★ Hugo環境はすでに構築している状態

D:\Dropbox\Hugo\Sites\testsite>pwd
/cygdrive/d/Dropbox/Hugo/Sites/testsite

D:\Dropbox\Hugo\Sites\testsite>cd ../

D:\Dropbox\Hugo\Sites>hugo new site Komittee-Express
Congratulations! Your new Hugo site is created in D:\Dropbox\Hugo\Sites\Komittee-Express.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/, or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>\<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.

D:\Dropbox\Hugo\Sites>cd Komittee-Express/

D:\Dropbox\Hugo\Sites\Komittee-Express>cd themes

D:\Dropbox\Hugo\Sites\Komittee-Express\themes>git clone https://github.com/kakawait/hugo-tranquilpeak-theme.git
Cloning into 'hugo-tranquilpeak-theme'...
remote: Counting objects: 3844, done.
remote: Compressing objects: 100% (100/100), done.
remote: Total 3844 (delta 53), reused 88 (delta 16), pack-reused 3710
Receiving objects: 100% (3844/3844), 16.71 MiB | 1.29 MiB/s, done.
Resolving deltas: 100% (2016/2016), done.
Checking connectivity... done.

D:\Dropbox\Hugo\Sites\Komittee-Express\themes>cd ../

D:\Dropbox\Hugo\Sites\Komittee-Express>hugo new posts/blog-environment.md
D:\Dropbox\Hugo\Sites\Komittee-Express\content\posts\blog-environment.md created

// GitHub連携

D:\Dropbox\Hugo\Sites\Komittee-Express>git init
Initialized empty Git repository in /cygdrive/d/Dropbox/Hugo/Sites/Komittee-Express/.git/

D:\Dropbox\Hugo\Sites\Komittee-Express>touch .gitignore

D:\Dropbox\Hugo\Sites\Komittee-Express>cd themes

D:\Dropbox\Hugo\Sites\Komittee-Express\themes>ls
hugo-tranquilpeak-theme

D:\Dropbox\Hugo\Sites\Komittee-Express\themes>rm -rf hugo-tranquilpeak-theme/.git

D:\Dropbox\Hugo\Sites\Komittee-Express\themes>d:

D:\Dropbox\Hugo\Sites\Komittee-Express\themes>cd d:\

d:\>pwd
/cygdrive/d

d:\>cd D:\Dropbox\Hugo\Sites\Komittee-Express

D:\Dropbox\Hugo\Sites\komittee-express>git remote add origin https://github.com/kunimi53chi/komittee-express.git

D:\Dropbox\Hugo\Sites\komittee-express>

// GitKrakenからプッシュ。GitHub連携および公開が完了。
// ここからNetlify上で設定する。

```

```
// Netlify

## Deploy settings

Repository: https://github.com/kunimi53chi/komittee-express
Build command: hugo --theme=hugo-tranquilpeak-theme
Publish directory: public/
Production branch: master
Branch deploys: Deploy only the production branch and its deploy previews

## Build environment variables

key=HUGO_VERSION
value=0.31.1

// サイトの名前を"komittee-express"に変更。config.tomlのbaseURLをNetlifyで生成されたURLに変更。

```

## postsが表示されない問題

`$ hugo -t hugo-tranquilpeak-theme` でbuildしてて、`public/`も出せてそうな感じなのに全然記事がでてこない。おもむろにNetlifyのDeploy logを貼る。

```
9:45:08 PM: Build ready to start
9:45:08 PM: Fetching cached dependencies
9:45:09 PM: No cached dependencies found. Cloning fresh repo
9:45:09 PM: git clone git@github.com:kunimi53chi/komittee-express
9:45:10 PM: git remote rm origin
9:45:10 PM: Preparing Git Reference refs/heads/master
9:45:11 PM: Running build command: hugo -t hugo-tranquilpeak-theme
9:45:13 PM: Downloading and installing node v6.12.2...
9:45:13 PM: Downloading https://nodejs.org/dist/v6.12.2/node-v6.12.2-linux-x64.tar.xz...
9:45:14 PM:
                                                                           0.0%
9:45:14 PM:
                                                                           1.1%
9:45:14 PM:
###
9:45:14 PM:
9:45:14 PM:  4.9%
9:45:14 PM:
##############
9:45:14 PM:
9:45:14 PM: 19.8
9:45:14 PM: %
9:45:15 PM:
##############################                                            4
9:45:15 PM: 2.1
9:45:15 PM: %
9:45:15 PM:
##########################################                                59.4%
9:45:15 PM:
9:45:15 PM: ##
9:45:15 PM: ##
9:45:15 PM: ##
9:45:15 PM: ##
9:45:15 PM: ##
9:45:15 PM: ####
9:45:15 PM: #
9:45:15 PM: #
9:45:15 PM: ##
9:45:15 PM: ###############################################
9:45:16 PM:  91.1%
9:45:16 PM:
######################################################################## 100.0%
9:45:16 PM:
9:45:16 PM: Computing checksum with sha256sum
9:45:16 PM: Checksums matched!
9:45:17 PM: Now using node v6.12.2 (npm v3.10.10)
9:45:17 PM: Using version v6.12.2 of node
9:45:17 PM: Using /opt/buildhome/.rvm/gems/ruby-2.1.2
9:45:17 PM: Installing Hugo 0.31.1
9:45:20 PM: Started building sites ...
9:45:20 PM:
Built site for language en:
0 draft content
0 future content
0 expired content
1 regular pages created
8 other pages created
9:45:21 PM: 0 non-page files copied
0 paginator pages created
0 tags created
0 categories created
total in 22 ms
9:45:21 PM: Build complete: exit code: 0
9:45:21 PM: Cleaning up docker container
9:45:21 PM: Starting to deploy site from 'public/'
9:45:22 PM: Deploying to CDN
9:45:24 PM: Starting post processing
9:45:24 PM: Post processing done
9:45:24 PM: Site is live
```

HugoのQuick Startと見比べてみると `0 paginator pages created` となっているのがな～んか怪しい。ローカルでも同じような状態になっている。

テーマを変えてみようか...　 Robustが日本人制作のテーマということで入れてみる。

`$ git clone https://github.com/dim0627/hugo_theme_robust.git`

...表示された！まさかThemeがあっていなかったとは思わなんだ。コード挿入箇所が見づらいけどなんとかしたい。

## 参考記事

- [Goで書かれたサイトジェネレーターHugoの紹介](http://hatebu.me/entry/hugo)
- [高機能ホスティングサービスNetlifyについて調べて使ってみた](https://qiita.com/TakahiRoyte/items/b7c4d1581df1a17a93fb)
    - ↑ Getting Startedによい
- [Netlify移行記: GitHub Pagesから独自ドメイン + Netlifyの引っ越しでやってきたこと](https://photo-tea.com/p/17/netlify-github-pages-hexo/)
    - ↑ さらなる環境整備によい
- [HTTPSの静的コンテンツをホストするならs3よりNetlifyが俺の求めていたものだった](https://qiita.com/shogomuranushi/items/6ab5bc29923b3f82c9ed)
- [2016年春版　静的サイトジェネレーターHugo導入Tips　①インストールとサイトの初期作成](https://qiita.com/biotist/items/ea860ebfb1214aacaf43)
- [2016年新機能!（GitHub Pages） GitHubのmasterブランチをWebページとして公開する手順](https://qiita.com/tonkotsuboy_com/items/f98667b89228b98bc096?utm_campaign=popular_items&utm_medium=referral&utm_source=popular_items)
- [NetlifyでHugoで作った静的サイトをホスティングしてビルドを自動化する](https://blog.mismithportfolio.com/web/hugo-netlify-build)
    - ↑ Getting Startedによい
- [Netlifyで静的サイトをホスティングする(1) アカウント作成 ～ GitHub連携](https://www.d4af.com/post/2017/10/netlify1/)
    - ↑ 一通り必要な設定事項を記述してくれている。
- [Netlify CMSでHugoに管理画面やエディタを追加して静的CMSをつくる](https://blog.mismithportfolio.com/web/netlify-cms)
