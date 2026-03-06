# lapras-management

Gemini CLIを使ってLAPRASに登録した情報を管理する。

## 必要なもの

- LAPRASのアカウントとAPIキー
  - APIキーは環境変数 `LAPRAS_API_KEY` に登録
- Node.js
  - バージョンは [.node-version](./.node-version) を参照

## セットアップ

```bash
npm ci
```

## Gemini CLIの起動

```bash
npm start
```

LAPRAS MCP Serverを使ってLAPRASの情報を取得・更新できる。

## 職務経歴書の出力

TBD

## 職務経歴書のプレビュー

```bash
npm run resume:preview
```

ブラウザでプレビューが表示される。
