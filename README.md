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