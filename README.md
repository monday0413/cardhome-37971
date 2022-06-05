# README

# テーブル設計

## users テーブル

| Column              | Type   | Options     |
| ------------------  | ------ | ----------- |
| nickname            | string | null: false |
| name                | string | null: false |
| email               | string | null: false unique: true|
| encrypted_password  | string | null: false |
|phone_number         | text   | null: false |
### Association

- has_many :cards
- has_one  :store
- has_one  :pop

## owners テーブル

|      Column               | Type      | Options     |
| ------------------------- | --------- | -----------  |
| store_name                | string    | null: false |
| store_address             | string    | null: false |
| store_phone_number        | text      | null: false |
| store_email               | string    | null: false |
|store_link                 |  text     |             |
|Card_color_id              | integer   | null: false |
|point_use                  | text      |             |
### Association

- has_one     :user
- belongs_to  :card
- has_many    :pops

______________________
## cards （カード） テーブル

| Column  | Type       | Options                        |
| ------  | ---------- | ------------------------------ |
| user    | references | null: false, foreign_key: true |
| store   | references | null: false, foreign_key: true |
| point   | string     | null: false                    |
### Association

- belongs_to :owner
- belongs_to :user


＿＿＿＿＿＿＿＿＿＿＿＿＿＿
## pops （ニュース) テーブル

| Column           | Type       | Options                        |
| ---------------- | ---------- | ------------------------------ |
| owner_id         | references | null: false, foreign_key: true |
| text             | text       | null: false                    |
### Association

- belongs_to :owner




