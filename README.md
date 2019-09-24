# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false, foreign_key: true|
|email|text|null: false, foreign_key: true|

### Association
- has_many :comments
- has_many :groups_users
- has_many :groups, thorough: :groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false, foreign_key: true|

### Association
- has_many :comments
- has_many :groups_users
- has_many :users, thorough: :groups_users


## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|comment|text|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
