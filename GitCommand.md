
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
