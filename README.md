# Claude Code プラグインマーケットプレイス

このディレクトリには、Claude Code用のカスタムプラグインマーケットプレイスが含まれています。

## 📁 構造

```
.
├── .claude-plugin/
│   └── marketplace.json          # マーケットプレイス設定
├── plugins/
│   ├── greeting-plugin/          # 挨拶プラグイン
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   └── commands/
│   │       ├── hello.md
│   │       └── goodbye.md
│   └── formatter-plugin/         # フォーマッタープラグイン
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── commands/
│       │   ├── format.md
│       │   └── review.md
│       └── agents/
│           └── code-analyzer.md
└── README.md                      # このファイル
```

## 🚀 使い方

### 1. マーケットプレイスを追加

```bash
cd /Users/mrsekut/Desktop/cc
claude
```

Claude Code内で：

```
/plugin marketplace add /Users/mrsekut/Desktop/cc
```

### 2. プラグインをインストール

#### 挨拶プラグイン

```
/plugin install greeting-plugin@custom-plugins-marketplace
```

**提供される機能：**
- `/hello` - 温かい挨拶をします
- `/goodbye` - お別れの挨拶をします

#### フォーマッタープラグイン

```
/plugin install formatter-plugin@custom-plugins-marketplace
```

**提供される機能：**
- `/format` - コードをフォーマットします
- `/review` - コードレビューを実行します
- `code-analyzer` エージェント - コード分析とリファクタリング提案

### 3. インストールの確認

```
/help
```

インストールしたプラグインのコマンドが表示されることを確認してください。

## 📦 含まれるプラグイン

### greeting-plugin

シンプルな挨拶機能を提供するプラグインです。Claude Codeの使用開始と終了を気持ちよくサポートします。

**バージョン:** 1.0.0

### formatter-plugin

コードのフォーマットとレビュー機能を提供する高度なプラグインです。コード品質の向上をサポートします。

**バージョン:** 1.0.0

**特徴：**
- 複数言語のフォーマット対応
- 包括的なコードレビュー
- 専門的なコード分析エージェント

## 🔧 カスタマイズ

### 新しいプラグインを追加

1. `plugins/`ディレクトリに新しいプラグインフォルダを作成
2. プラグイン構造を設定：
   ```bash
   mkdir -p plugins/your-plugin/.claude-plugin
   mkdir -p plugins/your-plugin/commands
   ```
3. `plugins/your-plugin/.claude-plugin/plugin.json`を作成
4. `.claude-plugin/marketplace.json`にプラグインを追加

### プラグイン構造

各プラグインには以下のディレクトリを含めることができます：

- `commands/` - カスタムスラッシュコマンド（.mdファイル）
- `agents/` - カスタムエージェント定義（.mdファイル）
- `skills/` - エージェントスキル（各スキルフォルダにSKILL.md）
- `hooks/` - イベントハンドラー（hooks.json）

## 📚 ドキュメント

- [プラグイン公式ドキュメント](https://docs.claude.com/ja/docs/claude-code/plugins)
- [プラグインリファレンス](https://docs.claude.com/ja/docs/claude-code/plugins-reference)
- [プラグインマーケットプレース](https://docs.claude.com/ja/docs/claude-code/plugin-marketplaces)

## 🤝 貢献

新しいプラグインの追加や既存プラグインの改善は歓迎します。

## 📝 ライセンス

MIT License

## 👤 作成者

Your Organization
