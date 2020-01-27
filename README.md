# Chat-space-2 DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages

## messagesテーブル
|column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|inreger|null: false, foreign_key: true|
### Assodiation
- belongs_to :user
- belongs_to :group

## goupsテーブル
|column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Assodiation
- has_many :messages
- has_many :groups_users 
- has_many :users, through: :groups_users

## group-usersテーブル
|column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Assodiation
- belongs_to :user
- belongs_tp :group
