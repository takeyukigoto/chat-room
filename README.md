# アプリ概要
## チャット投稿アプリ  
![メイン画像](read-chatmain.jpg)
### 詳細説明  
グループでコメント、画像が投稿できるアプリです。  
### 機能
AJAX非同期通信
### 使用技術
### 言語・ライブラリー
・Haml  
・CSS  
・JavaScript  
・jQuery  
・RAILS  
### 環境
・AWS EC2 S3   
・Capistrano 自動デプロイ

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
- has_many :tweets
  has_many :gropus,through,groups_user
  has_many :group_users


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|


### Association
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
