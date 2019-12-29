# ChatSpace_DataBase_plan
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false|
|Email|string|null: false|

### Association
- has_many :groups, through: :groups_users
- has_many :comments
- has_many :groups_users


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|

### Association
- has_many :users, through: :groups_users
- has_many :comments
- has_many :groups_users


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## commentsテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user