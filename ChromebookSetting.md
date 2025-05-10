
# Chromebook 便利設定

* デュアルモニター設定
* マウス設定
* VSCode導入
* Git導入

## デュアルモニター設定

1. 設定を選択
2. [デバイス] で [ディスプレイ] を選択
3. 内蔵ディスプレイではない方のディスプレイタブを選択（今回の場合は[X2483_2481]を選択）
4. [解像度] と [向き] を選択

## マウス設定

### マウスのスクロール加速度をOFFにする

1. 設定を選択
2. [デバイス] で [マウス] を選択
3. カーソルの[カーソルアクセラレーション]をOFFに変更

## VSCode導入

### インストール

1. [公式サイト](https://code.visualstudio.com/download)から[.deb]ファイルをダウンロード
2. ダウンロードした「code_〜.deb」ファイルをダブルクリック
3. [インストール]をクリック
4. インストールが完了したら[OK]をクリック

参考サイト） [ChromeBookにVSCodeを入れる方法と設定](https://gotoblog.org/chromebook-vscode/)

### 事前準備

#### 日本語化パッケージ

1. VSCode拡張機能[Markdown All in One]をインストール
2. VSCodeを再起動

#### 記述の補完機能

1. VSCode拡張機能[Japanese Language Pack for Visual Studio Code]をインストール

#### プレビュー

1. VSCode拡張機能[Markdown Preview Enhanced]をインストール

#### その他

1. [VsCodeの便利機能](https://m-training.github.io/blog/VsCodeSetting.html)を必要に応じてインストール

## Git導入

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
