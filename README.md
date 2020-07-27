# README


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
|name|integer|null: false|
|mail|integer|null: false|


### Association
-
- has_many :tweets
  has_many :gropus,through,groups_user
  has_many :group_users


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|


### Association
- 
- has_many :tweets
  has_many :users,through,groups_user
  has_many :groups_users

  ## tweetsテーブル

|Column|Type|Options|
|------|----|-------|
|comment|text|null: false|
|image|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user
