# Internship Application Manager

夏インターンや就活の応募状況を管理するためのWebアプリです。  
企業ごとの応募締切、提出物、選考状況、次にやることを一覧で管理できます。

## 概要

就活では、複数企業のインターンや本選考に同時並行で応募するため、締切や提出状況の管理が煩雑になりやすいです。  
このアプリでは、応募情報を一元管理し、締切順の確認や進捗状況の把握をしやすくすることを目的としています。

## 主な機能

- 企業名の登録
- 応募締切日の登録
- 必要書類の管理
- ES提出状況の管理
- Webテスト実施状況の管理
- 面接日程の管理
- 合否ステータスの管理
- 次にやることのメモ
- 締切順での表示
- 未完了タスクの確認
- 進捗率の表示

## 使用技術

- HTML
- CSS
- JavaScript
- Firebase Authentication
- Cloud Firestore
- GitHub Pages

## データ保存について

初期版では `localStorage` を用いたブラウザ内保存を想定しています。  
ただし、`localStorage` は同じブラウザ内でしかデータを保持できず、ブラウザのデータ削除や別端末利用には対応できません。

そのため、今後は以下の構成に変更する予定です。

- Firebase Authentication：ユーザー認証
- Cloud Firestore：ユーザーごとの応募情報保存

これにより、ログインしたユーザーが自分の応募情報を複数端末から確認・編集できるようにします。

## Firebase導入後のデータ構造案

```text
users
 └ userId
    └ applications
       └ applicationId
          ├ company
          ├ deadline
          ├ documents
          ├ esSubmitted
          ├ webTestDone
          ├ interviewDate
          ├ result
          └ nextAction
