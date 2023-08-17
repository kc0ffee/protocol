# README

このリポジトリは、Kloud ハッカソン#3 で作成するサービスの API についての定義がまとめられています。

API に関する仕様はこのリポジトリを参照してください。

## API に付いて

| API 名 | メソッド | 機能                                   | レスポンス     |
| :----- | :------- | :------------------------------------- | :------------- |
| theme  | GET      | サーバーからテーマの一覧を取得します。 | テーマリスト   |
| code   | POST     | サーバーに作成されたコードを送信します | 結果の ID など |
| result | GET      | サーバーから評価結果を取得する         | 評価結果       |

## レスポンス形式

### テーマの一覧を取得する API

```json
{
  "id": 1,
  "theme": "Hello Worldを出力する"
}
```

### コードをサーバーに送信する API

```json
// リクエストボディー
{
  "themeId": 1,
  "language": "ts",
  "code": "console.log(\"Hello World\")"
}
```

```json
{
  "id": 0,
  "themeId": 0,
  "code": "string",
  "timeStamp": "string"
}
```

### 評価結果を取得する API

```json
{
  "your_type": "Your Type",
  "type_description": "Type description",
  "code_line": 10,
  "token_len": 20,
  "token_count": 30,
  "function_len": 10
}
```
