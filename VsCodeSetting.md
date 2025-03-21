
# VsCodeの便利機能

* 拡張機能

---

## [GitGraph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)

VsCode上でGit操作できるようになる拡張機能

> 設定ではまったこと

1. vsCodeがgit.exeを認識しないとき

   * GitGraphの設定を開く。
   * git.pathで検索をかけて、「settings.jsonで開く」をクリック。
   * git.exeのインストール先を設定。

    ```settings.json
        "git.path": "D:\\Program Files\\Git\\Git\\bin\\git.exe",
    ```

    ※バックスラッシュは二つ必要（OK：'\\\\'、NG：'\\'）

    * [WinPCの環境変数の設定を確認](https://terakoya.sejuku.net/question/detail/35391)
      * 「システム環境変数」のリストから「Path」を選択
      * Gitのインストールパスを追加

    ```システム環境変数
        "git.path": "D:\\Program Files\\Git\\Git\\bin\\git.exe",
    ```

    * vsCodeを再起動
    * vsCode->表示->ターミナルを開く
    * vsCodeのターミナル上でGitコマンドが扱えるようになる。

## [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

VsCode上でmarkdownのスペルチェックを自動で行う拡張機能
