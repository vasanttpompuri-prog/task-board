# Task Board Project

## プロジェクト概要

タスク管理ボードアプリケーション。

## Git 運用ルール

### 基本方針

- **コードを変更するたびに必ずGitHubへプッシュする**
- `main` ブランチへの直接プッシュは禁止。必ずフィーチャーブランチを切ること
- コミットメッセージは日本語・英語どちらでも可。変更内容を簡潔に記述する

### ブランチ命名規則

```
feature/<機能名>   # 新機能追加
fix/<バグ名>       # バグ修正
chore/<作業名>     # リファクタリング・設定変更など
```

### コード変更時のフロー

1. フィーチャーブランチを作成する
2. 変更を加える
3. `git add` → `git commit` → **`git push`** を必ず行う
4. PRを作成してレビューを経てから `main` にマージする

### コミット前チェック

- テストが通ることを確認する（テスト環境がある場合）
- リントエラーがないことを確認する
- 機密情報（APIキー、パスワード等）がステージングされていないことを確認する

## 技術スタック

| 種別 | 技術 |
|---|---|
| フレームワーク | React 18 |
| ビルドツール | Vite 6 |
| 言語 | JavaScript (JSX) |
| スタイリング | Plain CSS（モジュールなし） |
| 状態管理 | React useState / useEffect |
| 永続化 | localStorage |
| デプロイ | GitHub Actions → GitHub Pages |

## コンポーネント命名規約

- コンポーネントファイル名・関数名は **PascalCase**（例: `App.jsx`, `TaskItem.jsx`）
- CSSクラス名は **kebab-case**（例: `.task-item`, `.add-btn`）
- イベントハンドラは **handle / on プレフィックス**（例: `handleKeyDown`, `onDelete`）
- ローカルストレージのキーは定数で管理（例: `const STORAGE_KEY = 'task-board-tasks'`）

## デプロイ先

**本番 URL**: https://vasanttpompuri-prog.github.io/task-board/

- `main` ブランチへのプッシュで GitHub Actions が自動ビルド＆デプロイ
- ワークフロー定義: `.github/workflows/deploy.yml`

## 開発ガイドライン

- コメントは原則書かない。WHYが非自明な場合のみ1行で記述する
- 不要なエラーハンドリングや抽象化は追加しない
- UIの変更を行った場合は、ブラウザで動作確認してから完了とする
