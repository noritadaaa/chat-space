# ChatSpace DB設計
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|password|string|null: false|
|email|string|null:false|

### Association
- has_many :groups
- has_many :posts

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|groupname|integer|null: false|
|user_id|integer|null: false, foreign_key: true|

### Association
- has_many :users

## postsテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|

### Association
belongs_to :user
belongs_to :group

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
