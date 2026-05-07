# tools

Masaさんの個人ツール集。Claude APIを使ったブラウザ完結型のHTMLツール群。

## ファイル構成
- `book-review.html` — AI読書レビューアシスタント

## book-review.html

### 概要
本の表紙写真またはタイトルを入力し、Claudeと対話しながら読書レビューを生成するツール。
note投稿用のレビューを2つのモードで作成できる。

### モード
- **対話モード** — 本の写真/タイトルを起点にClaudeと4〜6往復会話してレビューを生成
- **下書きモード** — Obsidianのメモをペーストして一発生成

### 技術仕様
- 単一HTMLファイル（サーバー不要・ブラウザで直接開ける）
- Claude API（`claude-opus-4-6`）をブラウザから直接呼び出し
- APIキーはlocalStorageに保存（外部送信なし）
- GitHub Pagesで公開中

### 筆者スタイル（下書きモード）
`DRAFT_SYSTEM_PROMPT` に「クジラのしっぽ」スタイルを定義済み。
- 口語体・タメ口・脱線あり
- 本の内容より自分の体験との紐付けを中心に
- 400〜700字程度

### モデル変更方法
`callClaudeWithSystem` 関数内の `model: 'claude-opus-4-6'` を変更する。

## 新しいツールを追加するときのルール
- 基本は単一HTMLファイルで完結させる
- APIキーが必要な場合はlocalStorageに保存する方式を踏襲
- ファイル名はわかりやすい英語で（例: `horoscope.html`）
