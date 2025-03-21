
# VsCodeの便利機能

* GitGraph
* markdownlint
* PlantUML

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

---

## [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

VsCode上でmarkdownのスペルチェックを自動で行う拡張機能

---

## [PlantUML](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml)

1. PlantUMLのjarファイルをセット
    * ダウンロード先：[PlantUML Downloads and Source Code](https://plantuml.com/ja/download)
    * ダウンロードファイル名：plantuml-mit-1.2025.2.jar

2. jarファイルを適当なフォルダに保存する
3. vSCodeの設定にjarファイルを登録する
   * 設定画面で「markdown-preview-enhanced.plantumlJarPath」を入力
   * Plantuml:Jarの項目に先ほど保存したjarファイルをフルパスで記載

参考にしたサイト：[VSCodeでPlantUMLを使うための環境構築](https://overworker.hatenablog.jp/entry/2024/02/17/231225)
