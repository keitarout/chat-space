## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index: true,null: false,unique: true|
|password|string|null: false|
|e-mail|string|null: false|

### Association

- has_many:groups, through:members
- has_many:messages
- has_many:members

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string||null: false,unique: true|
|user_id|integer|null: false, foreign_key: true|

### Association

- has_many:users, through:members
- has_many:messages
- has_many:members

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to: user
- belongs_to: group
