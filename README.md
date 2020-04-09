# DB設計

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|
|mail|string|
|password|string|

### Association
- has_many :messages
- has_many :groups
- has_many :groups, through: :groups_users 

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- belongs_to :user
- has_many :messages
- belongs_to :user, through: :groups_users

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|
|image|string|

### Association
- belongs_to :user
- belongs_to :groups
- belongs_to :groups_users