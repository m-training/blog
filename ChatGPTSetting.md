
# ChatGPT 便利設定

* 文字化け解消法

## 文字化け解消法

ChatGPTに図解を依頼すると文字化けする。
原因は、ChatGPTに日本語フォントが入っていないため。
文字化け解消法をいかに示す。

1. [Googleフォント](https://fonts.google.com/)にアクセスして、`Japanese`で検索
2. `Noto Sans Japanese`をダウンロード
3. `Noto_Sans_JP.zip`を解凍する
4. `NotoSansJP-VariableFont_wght.ttf`をChatGPTにアップロードする。
ttfファイルを添付して、以下のプロンプトで実行する。

    ```text
    アップロードしたフォントを用いてグラフを作成してください
    ```

参考サイト） [ChatGPTで「図解が文字化け」…そんなときは日本語フォントを渡せば解決します！](https://www.lifehacker.jp/article/2505_how_to_fix_japanese_character_encoding_in_chatgpt/)
