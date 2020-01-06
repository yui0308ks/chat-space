## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|name|string|null: false, foreign_key: true|
|email|string|null: false|
|password|string｜null: false|
### Association
- has_many :group, through: :groups_users
- has_many :message

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|name|integer|null: false, foreign_key: true| 
### Association
- has_many :message
- has_many :user, through: :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer｜null:false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user