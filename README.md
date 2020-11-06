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

# テーブル設計

## users テーブル

| Column      　| Type   | Options     |
| _________    | _______ | __________ |
| last_name     | string | null: false |
| name         | string | null: false |
| last_name_kana| string | null: false |
| name_kana    | string | null: false |
| email        | string | null: false |
| password     | string | null: false |
| nickname     | string | null: false |
| schedule    | references | null: false, foreign_key: true |



### Association

- has_many :comments
- has_many :studios 
- belongs_to :schedule

## comments テーブル

| Column     | Type    | Options     |
| ______     | ________ | ___________ |
| content | string     |                                |
| user    | references | null: false, foreign_key: true |
| studio    | references | null: false, foreign_key: true |
| schedule    | references | null: false, foreign_key: true |


### Association

- belongs_to :user
- has_many :studios
- belongs_to :schedule


## studios テーブル

| Column  | Type       | Options                        |
| ______  | __________ | ______________________________ |
| studio_name | string | null: false |
| category | string | null: false |
| schedule    | references | null: false, foreign_key: true |



### Association

- belongs_to :schedule
- has_one :comment
- belongs_to :user

## schedule テーブル

| Column      | Type       | Options       |
| ＿＿＿＿＿＿  | ＿＿＿＿＿   |  ＿＿＿＿＿_   |
| user    | references | null: false, foreign_key: true |
| studio    | references | null: false, foreign_key: true |



### Association
- belongs_to :user
- belongs_to :studio


