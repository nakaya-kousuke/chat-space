# DB設計

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
|id|int(10)|null: false,|
|name|varchar(100)|
|mail|varchar(100)|
|password|varchar(8)|


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|int(10)|null: false,|
|groupname|varchar(100)|
|chatmember|users_id|

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|varchar(1000)|
|image|string|