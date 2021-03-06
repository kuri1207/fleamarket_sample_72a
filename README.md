## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false, unique: true|
|email|string|null: false, unique: true|
|password|string|null: false|
|avatar|string||
|family_name|string|null: false|
|first_name|string|null: false|
|family_name_reading|string|null: false|
|first_name_reading|string|null: false|
|birth_day|integer|null: false|
|introduction|text||

### Association
- has_one :card
- has_many :items


## itemsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|price|integer|null: false|
|description|text|null: false|
|status|string|null: false|
|judgment|text||
|size|integer|null: false|
|cost|string|null: false|
|days|string|null: false|
|prefecture|integer|null: false, foreign_key: true|
|category|references|null: false, foreign_key: true|
|brand|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|

### prefecturenについて
active_hashのgemを使う


### Association
- belongs_to :user
- has_many :images
- belongs_to :category
- belongs_to :brand


## brandsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :items


## cards
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, unique: true|
|card_id|integer|null: false, unique: true|

### Association
- belongs_to :user

## destinationsテーブル
|Column|Type|Options|
|------|----|-------|
|family_name|string|null: false|
|first_name|string|null: false|
|family_name_reading|string|null: false|
|first_name_reading|string|null: false|
|post_code|integer|null: false|
|prefecture|ineteger|null: false|
|city|string|null: false|
|adress|string|null: false|
|building_name|string||
|phone_number|integer|null: false, unique: true|
|user|references|null: false, foreign_key: true|

### Association
- belongs_to :user


## imagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|null: false|
|item|references|null: false, foreign_key: true|

### Association
- belongs_to :item


## categorysテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|ancestry|string|null: false|

### Association
- has_many :items
has_ancestry

### ancestryについて
ancestryのgemを使う



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
