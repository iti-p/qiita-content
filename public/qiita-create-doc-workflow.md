---
title: qiita-create-doc-workflow
tags:
  - ''
private: false
updated_at: ''
id: null
organization_url_name: null
slide: false
ignorePublish: false
---
# Qiita CLI を使った記事の作成と投稿手順

## 記事の新規作成
コマンドプロンプト上で以下を実行し、記事ファイルを新規作成します。

```
npx qiita new [記事名]
```

---

## 作業ブランチの新規作成
作業用のブランチを作成し、切り替えます。

```
git checkout -b feature/[記事名]
```

---

## 〜 作成作業 Start 〜

### 1. 生成AIによる草案作成  
記事の草案を生成AIで作成します。

### 2. 修正作業  
生成AIの草案を元に内容を修正します。

### 3. 生成AIによる添削  
修正内容を生成AIに添削してもらいます。修正指示があれば再度修正作業へ戻ります。

### 4. タグの付与  
記事のYAMLフロントマターに必要なタグを記入します。

---

## 作業を中断するとき
作業途中で中断する場合は、変更内容をコミットしておきます。

```
git add .
git commit -m "途中経過のコミット"
```

---

## 〜 作成作業 End 〜

---

## 作業ブランチのマージ
作業が完了したら作業ブランチをmainやmasterにマージします。

```
git checkout main
git merge feature/[記事名]
```

必要に応じてリモートリポジトリへプッシュします。

```
git push origin main
```

---

## Qiita上での確認
Qiita CLIで記事のプレビューや投稿状況を確認します。

```
npx qiita preview [記事名]
```

記事に問題がなければ、プレビュー画面の「記事を投稿する」から投稿します。

---

## 修正が必要な場合
問題が見つかったら、作業ブランチに切り替えて再度編集・修正を行います。

---

以上がQiita CLIで記事を作成し投稿するまでの一連の手順の概要です。