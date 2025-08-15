
# Python 便利設定

- [Python 便利設定](#python-便利設定)
  - [使用原則](#使用原則)
  - [初回に実施する設定](#初回に実施する設定)
  - [作業開始前のお作法](#作業開始前のお作法)
    - [1) 作業用環境を有効化](#1-作業用環境を有効化)
    - [2) 確認（どの Python を使っているか）](#2-確認どの-python-を使っているか)
  - [パッケージ導入の作法](#パッケージ導入の作法)
    - [事前に作業用環境を有効化しておくこと](#事前に作業用環境を有効化しておくこと)
    - [pip は “その環境の Python 経由” で使う](#pip-は-その環境の-python-経由-で使う)

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

2. PowerShell を再起動

3. base 自動有効化を止める

    ```powershell
    conda config --set auto_activate_base false
    ```

4. Windows設定

    設定 → アプリ → アプリ実行エイリアス → python.exe / python3.exe を OFF

## 作業開始前のお作法

### 1) 作業用環境を有効化

```powershell
conda activate ai311
```

### 2) 確認（どの Python を使っているか）

```powershell
where.exe python
python --version
python -m pip --version
python -c "import sys; print(sys.executable)"
```

## パッケージ導入の作法

### 事前に作業用環境を有効化しておくこと

```powershell
conda activate ai311
```

### pip は “その環境の Python 経由” で使う

```powershell
python -m pip install openai  # 例
```
