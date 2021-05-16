---
title:  GitHubで複数アカウントを使うにはHTTPS接続が楽
tags:
  - Git

---

「GitHub 複数アカウント」で検索すると様々な解決方法が出てくるけど、真似してあれこれ試した結果、一番手軽だった方法はHTTPS接続することだったので記録として残しておく。

<!--more-->
<br>

#### 前提

- Git & GitHub 初心者が嵌ったときの参考に。あと、自分自身の備忘録にも。
- 実行環境はMacOS Catalina (10.15.4)、Git ver. 2.24.2、Sourcetree ver. 4.0.2
- SourcetreeのGUI操作で `git clone` まで済ませてから、VSCode、RStudioなど好きな環境でリポジトリ管理する方針
- GitHubをメインアカウント（SSH認証済み）とサブアカウント（こちら）で使い分けたい
- メインアカウントで `git config --global` の設定を済ませている
- Sourcetreeにはメイン・サブ両方のアカウントを登録済み

<br>

去年の年末からサブ垢のgitまわりがまともに動かせずにいて、webサイトの制作もままならない状態だった。SSHの設定を変えたりターミナルでgit configの操作をしても埒があかないので、GUI（Sourcetree）の助けを借りたらうまくいくようになった。

冷静に考えれば、 `~/.ssh/config` でSSHの設定を煩雑にするよりも、サブ垢だけSSH認証を介さずにHTTPSで接続すれば、それで解決することだったのだ。

<br>

#### 手順

※色々設定をいじったので、正確に再現できていない箇所もあるかも

1. GitHubでリポジトリを作成し、URLをHTTPSに切り替えてからコピーする。

2. Sourcetreeで、新規→URLからクローン→1のURLをペースト。

3. 2のURLを次のように書き換える。（下記 `user.name` にサブアカウント名を入れる）

   `https://user.name@github.com/user.name/repository-name.git`

4. 保存先のパスを決めてクローン。

5. リポジトリ画面を開く→設定→高度な設定→グローバルユーザー設定を使う のチェックを外して、サブアカウントのユーザー名とメールアドレスを入力。

6. 設定→リモート→リモートリポジトリのパス、「configファイルを編集」の2ヶ所も念のため確認して、3の設定が抜けていたら書き足す。user.name, user.emailが間違っていないかも確認。

7. 6までの操作で、クローンしたリポジトリの `git config --local` が設定される。ローカルのフォルダにファイルを追加すれば、commit, pushができる。

8. サブアカウントでの初回認証のみ、pushのときにGitHubアカウントのパスワードを聞かれる。Macでは、2回目以降はキーチェーンアクセスに保存されたパスワードを参照するので聞かれなくなる模様。

9. あとは好きな開発環境でGitを使うだけ。

<br>

#### 参考にしたサイト

- [SourceTree で複数アカウントを扱う](http://mattsudev.hatenablog.com/entry/2015/06/19/182416)
- [sourcetreeで複数のgitアカウント管理](https://qiita.com/A-Kira/items/0f5334919e330a95f198)
- [GitHubの複数アカウントを使い分けるならSSHよりhttpsの方がいいんじゃね？という話](https://qiita.com/zaki-yama/items/bfb0c2bef516af58c3fa)
- [GitHub – 複数のアカウントを追加してHTTPS接続で切り替える方法](https://howpon.com/4738)
