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
- has_many :messages
- has_many :groups_users
- has_many through :groups

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|body|text|
|image|string|
|group_id|integer|null: false,foreign_key: true|
|user_id|integer|null: false,foreign_key: true|
|timestamps|integer|null: false|

### Association
- belongs_to :users
- belongs_to :groups

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|group_name|text|null: false|

### Association
- has_many :messages
- has_many :groups_users
- has_many through :users


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :groups
- belongs_to :users

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
