# SortScreenshot — スクリーンショット整理スクリプト

> 指定フォルダ内のファイルを作成日ごとに自動で仕分ける、macOS 向け Bash スクリプト。

---

## 概要

**SortScreenshot** は、`TARGET_DIR` 配下のファイルを `YYYY-MM-DD` 形式の日付フォルダへ移動するシンプルなユーティリティです。

- ファイルの作成日を取得して日付ごとに分類
- 日付フォルダがなければ自動作成
- 単体スクリプトで動作し、追加依存なし

---

## 機能

| 機能 | 説明 |
|------|------|
| 日付取得 | `stat` を使ってファイルの作成日を取得 |
| 自動フォルダ作成 | `YYYY-MM-DD` のディレクトリを必要時に作成 |
| ファイル移動 | 対象ファイルを該当日付ディレクトリへ移動 |
| 環境変数設定 | `.env` の `TARGET_DIR` から整理対象を指定 |

---

## 技術スタック

| カテゴリ | 技術 |
|----------|------|
| OS | macOS |
| スクリプト | Bash |
| 日付取得 | BSD `stat`（`stat -f`） |

---

## セットアップ

### 必要環境

- macOS
- Bash

### インストール

```bash
# 1. リポジトリをクローン
git clone https://github.com/unoharu/SortScreenshot.git
cd SortScreenshot

# 2. .env を作成して整理対象を指定
cat << 'EOF' > .env
TARGET_DIR=/path/to/your/ScreenShot
EOF

# 3. 実行権限を付与
chmod +x sort_files.sh
```

### 実行

```bash
./sort_files.sh
```

---

## 使い方（アプリ化）

macOS のスクリプトエディタ（Script Editor）を使うと、アプリとして起動できます。

```applescript
do shell script "/path/to/your/sort_files.sh"
```

---

## ディレクトリ構成

```
SortScreenshot/
├── sort_files.sh   # ファイルを日付ごとに整理する本体スクリプト
├── .env            # 整理対象ディレクトリ（TARGET_DIR）
└── README.md       # このドキュメント
```

---

## 環境変数

`.env` に以下を設定してください。

| 変数名 | 説明 | 例 |
|--------|------|----|
| `TARGET_DIR` | 整理対象のディレクトリ絶対パス | `/Users/you/Desktop/ScreenShot` |

---

## 注意事項

- スクリプトは **移動（`mv`）** を行うため、実行後に元ディレクトリからファイルはなくなります。
- `.env` の `TARGET_DIR` が誤っていると意図しない場所を整理する可能性があります。
- macOS の `stat -f` を使用しているため、Linux 環境ではそのまま動作しません。

---

## 実行デモ

![Sort_ScreenShot](https://github.com/user-attachments/assets/890a14da-5ac9-4884-9394-b0f015105f16)
