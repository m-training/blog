
# Windows11 便利設定

* 右クリックをデフォルトで前表示する（Win10仕様に戻す）

## 右クリックをデフォルトで前表示する（Win10仕様に戻す）

1. スタートメニューを右クリックし、「Windows ターミナル（管理者）」を選択

2. ターミナルに以下のコマンドを入力

    ```Terminal
    reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
    ```

3. Enterキーを押下して「この操作を正しく終了しました。」と表示されたことを確認
