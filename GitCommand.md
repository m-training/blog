
# Gitコマンド

- [Gitコマンド](#gitコマンド)
  - [起動](#起動)
  - [準備](#準備)
    - [パッケージインストール](#パッケージインストール)
    - [Gitセットアップ](#gitセットアップ)
    - [SSH設定](#ssh設定)
      - [公開鍵の生成](#公開鍵の生成)
      - [公開鍵の登録](#公開鍵の登録)
    - [クローン](#クローン)
      - [前提](#前提)
      - [実行](#実行)
  - [アップロード](#アップロード)
  - [ブランチ作成](#ブランチ作成)
    - [その他](#その他)
  - [ログ確認](#ログ確認)
  - [リモートリポジトリからプル](#リモートリポジトリからプル)
  - [有用情報](#有用情報)

---

## 起動

1. 該当フォルダを右クリックして、「Open Git Bash here」を選択する。

---

## 準備

### パッケージインストール

1. ターミナルを開く。
2. パッケージを更新するだめに以下のコマンドを入力する。

    ```git
    sudo apt update -y
    sudo apt upgrade -y
    sudo apt full-upgrade -y
    ```

参考サイト） [ChromeOSでGit, VSCode, Dockerをインストールして開発](https://qiita.com/pyama2000/items/90b189964f71def53b19)

### Gitセットアップ

1. configを設定する。

    ```git
    git config --global user.name "ｍ−training"
    git config --global user.email "mmtir5kw344@gmail.com"
    ```

参考サイト） [git のセットアップができていない](https://qiita.com/TkTkTkTkTako/items/2400864e5f12ba70dc6d#%E8%A7%A3%E6%B1%BA%E6%96%B9%E6%B3%95%E8%A9%B3%E7%B4%B0)

### SSH設定

#### 公開鍵の生成

1. 以下のコマンドを入力して接続状況を確認する。

    ```git
    ssh -T git@github.com
    ```

    * 成功の場合

    ```git
    Hi m-training! You've successfully authenticated, but GitHub does not provide shell access.
    ```

    * 失敗の場合

    ```git
    Warning: Permanently added the RSA host key for IP address '***' to the list of known hosts.
    git@github.com: Permission denied (publickey).
    ```

2. 以下のコマンドを入力して公開鍵を確認する。

    ```git
    cd ~/.ssh
    ```

    ```git
    ls -a
    ```

3. 以下のファイルがあるか確認する。
   * id_rsa
   * id_rsa.pub

4. 公開鍵がない場合は、以下のコマンドで生成する。
   Enter連打でOK

    ```git
    ssh-keygen -t rsa
    ```

5. [id_rsa.pub]ファイルの内容を確認する。

    ```git
    cat id_rsa.pub
    ```

6. [id_rsa.pub]ファイルの内容をコピーする。

#### 公開鍵の登録

1. githubの自分のアイコンをクリックして、[Settings]をクリック。
2. [SSH and GPG keys]をクリック
3. [SSH keys]の[Title]と[Key]を入力する。
   * [Title]は任意の名前。公開鍵の種類がわかれば良い。
   * [Key]には[id_rsa.pub]の内容を貼り付ける。

4. 以下のコマンドを入力して接続状況を確認する。

    ```git
    ssh -T git@github.com
    ```

    * 成功の場合

    ```git
    Hi m-training! You've successfully authenticated, but GitHub does not provide shell access.
    ```

### クローン

#### 前提

* クローン元：<https://m-training.github.io/blog/>
* クローン先：/D/01_MyData/04_PAS/06_Git

#### 実行

1. github上で「<>Code」をクリック

2. SSHタブ下部の<git@github.com>:...をコピー

3. WinPC上でカレントディレクトリ移動

    ```git
    cd D:\01_MyData\06_Git
    ```

4. クローン実施

    ```git
    git clone git@github.com:m-training/blog.git
    ```

5. .gitフォルダの確認。
    [.git]が生成されていることを確認する。

    ```git
    ls -a
    ```

6. リモートリポジトリとローカルリポジトリの紐づき確認

    ```git
    git remote -v
    ```

    以下のように表示されればOK。

    ```git
    origin  https://github.com/m-training/blog.git (fetch)
    origin  https://github.com/m-training/blog.git (push)
    ```

---

## アップロード

1. ステージ

    ```git
    git add README.md
    ```

    ※変更を加えたファイルを一括アップロードする場合

    ```git
    git add --all
    ```

2. コミット（コミットメッセージが2行の場合）

    ```git
    git commit -m "git command add" -m "clone command"
    ```

3. プッシュ

    ```git
    git push origin main
    ```

---

## ブランチ作成

1. ブランチの一覧確認

    ```git
    git branch -a
    ```

2. ブランチを作成

    ```git
    git checkout -b 作成するブランチ名
    ```

3. ブランチをリモートに登録

    ```git
    git push -u origin 作成したブランチ名
    ```

### その他

* ブランチの移動

    ```git
    git checkout 移動先のブランチ名
    ```

---

## ログ確認

* コミット履歴を1行で表示

    ```git
    git log --oneline
    ```

* コミット履歴をグラフィカルに表示

    ```git
    git log --graph
    ```

---

## リモートリポジトリからプル

* プルする

    ```git
    git pull origin main
    ```

* コンフリクトが発生している場合は、変更箇所を確認

  * 例：「=======」の上部が古いローカルデータ、下部がリモートのデータ
    どちらか必要な方を残して編集する。

    ```git
    <<<<<<< HEAD
    * [x] 「ゴルフ場殺人事件」感想文共有
    * [ ] ウルトラ図解 不安障害・パニック
    * [ ] 自転車整備
    * [ ] 中小企業診断士 はじめの一歩
    * [ ] Udemy「はじめての会計学」受講
    =======
    * [x] ウルトラ図解 不安障害・パニック
    * [x] Microsoftアカウント認証不具合対応
    >>>>>>> b4f171515f51b0f782c21738cfbf1b67f703861c
    ```

* 編集が完了したらファイルを上書き保存して、[アップロード](#アップロード)を実施。

---

## 有用情報

* `git init`と`git clone`の違い
  Q：
  新しくプロジェクトを作る時git cloneする前にgit initしなくて大丈夫なんでしょうか？
  
  A：
  はい、大丈夫です。git init してから git clone することもできますが、いきなり git clone するときとは違うことが起きていることは理解しておいたほうがいいかもしれません。
  **git init は、「今いるディレクトリを Git で管理したいから、準備をよろしく」という意味のコマンドです。** これを実行すると、Git のデータを入れるための .git という隠しディレクトリができます。これができる場所に注意してください。ご想像の通り、今いるディレクトリです。もちろん、commit 後に push されるのも、今いるディレクトリです。要は、今はリポジトリの「中」にいる状態ですね。
  これに対して、**git clone したときには、今いるディレクトリの「サブディレクトリとして」リポジトリが clone されます。clone した瞬間、リポジトリの一つ上の階層にいることになるわけです。.git があるのも今いるディレクトリではなく、clone したサブディレクトリの中です。**
  おさらいすると、git init してから git clone すると、.git は二つできるわけですね。ひとつは今いるディレクトリに、もう一つはサブディレクトリの中に──これらは互いに無関係です。

[引用：QuoraのQA](https://jp.quora.com/%E6%96%B0%E3%81%97%E3%81%8F%E3%83%97%E3%83%AD%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%82%92%E4%BD%9C%E3%82%8B%E6%99%82git-clone%E3%81%99%E3%82%8B%E5%89%8D%E3%81%ABgit-init%E3%81%97%E3%81%AA%E3%81%8F%E3%81%A6%E5%A4%A7)
