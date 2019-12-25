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


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, unique: true|
|name|string|null: fslse|
|user_id|integer|null: false, foreign_key: true|
|massege_id|integer|null: false, foreign_key: true|

### Association
-  has_many :users_groups
-  has_many :users, through::groups_users


## massagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, unique: true|
|body|text|null: false|
|image|string|
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

