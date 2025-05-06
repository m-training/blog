
# Gitコマンド

* 起動
* 準備
* アップロード
* ブランチ作成
* ログ確認

---

## 起動

1. 該当フォルダを右クリックして、「Open Git Bash here」を選択する。

---

## 準備

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

2. SSHタブ下部のgit@github.com:...をコピー

3. WinPC上でカレントディレクトリ移動

    ```git
    cd D:\01_MyData\06_Git
    ```

4. クローン実施

    ```git
    git clone git@github.com:m-training/blog.git
    ```

---

## アップロード

1. ステージ

    ```git
    git add README.md
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
