---
title: qiita-create-doc-workflow
tags:
  - qiita
  - cli
  - workflow
private: false
updated_at: ''
id: null
organization_url_name: null
slide: false
ignorePublish: false
---

# Qiita CLIによる記事作成と投稿手順

Qiita CLIで記事を作成し、管理・投稿まで行う標準のワークフローを記載する。

## 記事の新規作成
コマンドプロンプト上で以下のコマンドを実行し、記事ファイルを新規作成する。

```

npx qiita new [記事名]

```

---

## 作業ブランチの新規作成
作業用ブランチを作成し、切り替える。

```

git checkout -b feature/[記事名]

```

---

## 作成作業（start）
- 生成AIで草案を作成する
- 草案を修正する
- 生成AIで添削する。修正点があれば再度修正
- タグをYAMLフロントマター（記事冒頭）に記載する

---

## 作業を中断する場合
作業途中で中断する際は、変更内容をコミットしておく。

```

git add .
git commit -m "途中経過のコミット"

```

---

## 作成作業（end）

---

## 作業ブランチのマージとプッシュ
作業が完了したらmainブランチへマージし、リモートリポジトリに反映する。

```

git checkout main
git merge feature/[記事名]
git push origin main

```

---

## Qiita上での確認と投稿
Qiita CLIで記事のプレビューや投稿状況を確認する。

```

npx qiita preview [記事名]

```

問題がなければプレビュー画面から「記事を投稿する」を選択する。

問題が見つかった場合、作業ブランチで再編集・修正を行う。

---

以上がQiita CLIを使った記事作成・投稿の基本的な手順である。

