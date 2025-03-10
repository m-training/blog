
# Gitコマンド

* 起動
* 準備
* アップロード

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

1. カレントディレクトリ移動

    ```git
    cd /D/01_MyData/04_PAS/06_Git
    ```

2. クローン実施

    ```git
    git clone https://m-training.github.io/blog/
    ```

---

## アップロード

1. ステージ

    ```git
    git add README.md
    ```

2. コミット

    ```git
    git commit -m"よく使うGITコマンドを追記"
    ```

3. プッシュ

    ```git
    git push origin main
    ```
