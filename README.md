# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|email|integer|null: false,unique: true|
|password|integer|null: false|
|nickname|integer|null: false|

### Association
- has_many :message
- has_many :groups_user
- has_many through :group

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|body|text|null: false|
|image|string|null: false|
|group_id|integer|null: false,foreign_key: true|
|user_id|integer|null: false,foreign_key: true|
|timestamps|integer|null: false|

### Association
- belongs_to :user
- belongs_to :group
- belongs_to :groups_user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|group_name|text|null: false|

### Association
- has_many :message
- has_many :groups_user
- has_many through :user


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
- has_many :message
* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
