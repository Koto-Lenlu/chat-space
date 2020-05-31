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
|name|string|null: false,　add_index, unique: true|
|email|string|null: false, unique: true|
|password|string|null: false|

### Association
- has_many :groups ,through: :groups_users
- has_many :message

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|

### Association
- has_many :users ,through: :groups_users
- has_many :message

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string| |
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
