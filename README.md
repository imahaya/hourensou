# hourensou DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique|
|password|string|null: false, unique|
|nickname|string|null: false, unique, index: true|
### Association
- has_many :posts

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|null: false|
|user|references|null: false, foreign_key: true|
### Association
- belongs_to :user