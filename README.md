# README


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, unique: true|
|name|string|null: false|
|e-mail|string|null: false, unique:true|
|password|string|null: false, unique: true|

### Association
-  has_many :groups_users
-  has_many :users,through::groups_users
-  has_many :messages


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, unique: true|
|name|string|null: false|

### Association
-  has_many :users_groups
-  has_many :users, through::groups_users
-  has many :masseges


## massagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, unique: true|
|body|text|null: false|
|image|string|null: false|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
-  belongs_to :user
-  belongs_to :group


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

