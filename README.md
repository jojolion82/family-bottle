# アプリケーション名 

familyーbottle


# アプリケーション概要

ファミリーボトルは、家族のメンバーが思い出やメッセージをボトルに込めて共有するWebサービスです。家族間のコミュニケーションや絆を深めるためのプラットフォームとして設計します。


## 機能

- ボトルの作成：家族のメンバーは自由な内容を持つボトルを作成できます。
- テーマ設定：ボトルにはテーマを設定して、共有する内容を絞り込むことができます。
- コメント機能：他のメンバーのボトルに対してコメントを残すことができます。
- 家族グループ：家族ごとに専用のグループを作成して、グループ内でボトルの共有が可能です。
- 通知機能：新しいボトルやコメントが投稿された際に、メール通知を受け取ることができます。

## インストールとセットアップ
- このリポジトリをクローンします。
- 必要なGemをインストール
- bundle install
- rails db:create
- rails db:migrate
- rails s
- ブラウザでhttp://localhost:3000にアクセスします。


# 使用技術
Ruby on Rails
HTML, CSS, JavaScript
PostgreSQL (データベース)
Devise (ユーザーアカウント認証)


## usersテーブル
| Column               | Type   | Option                    | 
| -------------------- | ------ | ------------------------- | 
| username             | string | null: false               |
| email                | string | null: false, unique: true |
| password             | string | null: false               |
| user_created_at      | date   | null: false               | 
| user_updated_at      | date   | null: false               | 

## family_groupsテーブル
| Column                | Type   | Option                   | 
| --------------------- | -------| ------------------------ | 
| group_name            | string | null: false              | 
| family_created_at     | date   | null: false              | 
| family_updated_at     | date   | null: false              | 

##  bottlesテーブル
| Column            | Type       | Option                         | 
| ----------------  | ---------- | ------------------------------ | 
| content           | text       | null: false                    | 
| theme             | string     | null: false                    | 
| user_id           | integer    | foreign key (users.id)         | 
| group_id          | integer    | foreign key (family_groups.id) | 
| bottle_created_at | integer    | null: false                    | 
| bottle_updated_at | integer    | null: false                    | 

## commentsテーブル
| Column                | Type    | Option                   | 
| --------------------- | ------  | ------------------------ | 
| comment               | text    | null: false              | 
| bottle_id             | integer | null: false              | 
| family_created_at     | date    | null: false              | 
| family_updated_at     | date    | null: false              | 