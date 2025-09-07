
# Python 便利設定

- [Python 便利設定](#python-便利設定)
  - [使用原則](#使用原則)
  - [初回に実施する設定](#初回に実施する設定)
  - [Python プロジェクトセットアップ手順](#python-プロジェクトセットアップ手順)

---

## 使用原則

- base は汚さない（実務用パッケージは入れない）
- パッケージ導入は python -m pip install ... を徹底
- 使う前に conda activate ai311（＝作業用環境を有効化）

## 初回に実施する設定

1. Miniforge をインストール後、「Miniforge Prompt」を開いて初期化

    ```powershell
    conda init powershell
    ```

   - 目的:
     - PowerShellでcondaコマンドを使えるようにする
     - 環境変数のPATHを自動設定
     - conda環境の切り替えを可能にする
       →これによりconda activateなどのコマンドが使用可能に

2. PowerShell を再起動

3. base 自動有効化を止める

    ```powershell
    conda config --set auto_activate_base false
    ```

   - 目的:
     - PowerShell起動時に自動的にbase環境が有効化されるのを防ぐ
     - プロジェクトごとに適切な環境を明示的に選択できるようにする
       →必要な時だけconda activate baseで有効化できる

4. Windows設定

    設定 → アプリ → アプリ実行エイリアス → python.exe / python3.exe を OFF

   - 目的:
     - Microsoft StoreのPythonとの競合を防ぐ
     - インストールしたPythonを確実に使用する

> **重要ポイント**
>
> - これらの設定は一度だけ実行すれば良い
> - 新しいPCやクリーンインストール時に必要
> - 複数のPython環境を適切に管理するための基本設定

---

## Python プロジェクトセットアップ手順

1. プロジェクト環境の準備

   - プロジェクトフォルダの作成

   ```powershell
   cd D:\02_Learning_python
   mkdir プロジェクト名
   cd プロジェクト名
   ```

   - 仮想環境の作成

   ```powershell
   # 仮想環境の作成
   conda create -p .\venv python=3.11

   # 仮想環境の有効化
   conda activate .\venv
   ```

   - 必ず環境を有効化してから作業を開始
   - 誤った環境へのインストールを防止

   >重要: プロジェクトごとに独立した仮想環境を作成することで、依存関係の競合を防ぎます。

2. VS Code の設定

   - Python インタプリタの選択
     - Ctrl + Shift + P でコマンドパレットを開く
     - "Python: Select Interpreter" を選択
     - .\venv\python.exe を選択

   >注意: 正しいインタプリタを選択しないと、パッケージのインストールやスクリプトの実行で問題が発生します。

   - 仮想環境の確認

   ```powershell
   # 仮想環境の一覧表示
   conda info --envs

   # アクティブな環境に * マークが付いていることを確認
   ```

3. パッケージのインストール

   - 基本パッケージのインストール

   ```powershell
   # 仮想環境が有効化されていることを確認してから実行
   python -m pip install パッケージ名
   ```

   - なぜ python -m pip を使うのか:
     - システムのデフォルトpipではなく、現在の環境のpipを確実に使用
     - パッケージが正しい環境にインストールされることを保証
   - 注意点:
     - pip install は非推奨（環境の混乱を招く可能性）
     - 常に python -m pip install を使用
