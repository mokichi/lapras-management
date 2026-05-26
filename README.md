# lapras-management

[LAPRAS](https://lapras.com) に登録されているエンジニア活動の情報を [Claude Code](https://claude.ai/code) を使って管理・活用するためのリポジトリです。

「Resume as Code」の考え方をベースに、AIエージェントが職務経歴書を常に最新の状態に保つことを支援します。

## 主な機能

- **AIによる職務経歴書の自動生成**: LAPRAS MCP Server 経由で取得した最新の経歴データを基に、Claude Code が Markdown 形式の職務経歴書を生成します。
- **Resume as Code**: 職務経歴書をソースコードのように管理。AIとの対話を通じて、表現の推敲や構成の変更を即座に行えます。
- **LAPRAS MCP Server 連携**: LAPRASに登録した経歴の取得だけでなく、AIを介した情報の更新も可能です。

## 必要なもの

- **LAPRAS アカウント & APIキー**
  - [LAPRAS](https://lapras.com) で APIキー を発行し、環境変数 `LAPRAS_API_KEY` に設定してください。
- **Node.js**
  - バージョンは [.node-version](./.node-version) を参照してください。
- **Claude Code**
  - インストール方法は [公式ドキュメント](https://docs.anthropic.com/ja/docs/claude-code) を参照してください。

## セットアップ

```bash
# 依存パッケージのインストール
npm ci
```

## 使い方

### 1. AIエージェント（Claude Code）の起動

プロジェクトディレクトリで Claude Code を起動します。

```bash
claude
```

### 2. 職務経歴書のビルド

Claude Code に「職務経歴書を出力して」と指示するか、`/resume-builder` コマンドを実行すると、`outputs/resume_YYYYMMDD.md` に職務経歴書が出力されます。

### 3. 職務経歴書のプレビュー

最新の職務経歴書をブラウザで確認できます。

```bash
npm run preview
```

### 4. 職務経歴書のPDF化

最新の職務経歴書をPDF化します。

```bash
npm run pdf
```

## ディレクトリ構成

- `.claude/commands/resume-builder.md`: 職務経歴書生成コマンドの定義。
- `.claude/settings.json`: Claude Code の設定（MCP Server 等）。
- `skills/resume-builder/`: 職務経歴書生成のためのテンプレートやリファレンス情報。
- `outputs/`: 生成された職務経歴書の出力先。
