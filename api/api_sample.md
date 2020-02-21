FORMAT: 1A

# レシピサイトWebAPIドキュメント

## すべてのレシピのXMLを表示する [/recipes]

### recipes_list [GET]
すべてのレシピのリストを返します。

+ Response 200 (application/json)
    + Attributes
        + success: False (boolean) - ステータス
        + path (array) - XMLファイルパス
        + error: show not implemented yet (string) - エラーメッセージ