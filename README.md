# テーブル設計
## users テーブル

| Column           | Type    | Options     |
| ---------------- | ------- | ----------- |
| first_name       | text    | null: false |
| family_name      | text    | null: false |
| kanafirst_name   | text    | null: false |
| kanafirmily_name | text    | null: false |
| email            | text    | null: false |
| password         | text    | null: false |
| nickname         | text    | null: false |
| birth_y          | integer | null: false |
| birth_m          | integer | null: false |
| birth_d          | integer | null: false |

### Association

- has_many :sales
- has_many :items, through: sales
- has_many :items
- has_many :addresses

## items テーブル

| Column   | Type       | Options                        |
| -------- | ---------- | ------------------------------ |
| seller   | references | null: false, foreign_key: true |
| name     | text       | null: false                    |
| stock    | boolean    |                                |  
| price    | integer    | null; false                    |   
| category | text       | null; false                    | 
| status   | text       | null; false                    | 
| charge   | boolean    |                                | 
| area     | text       | null; false                    | 
| date     | date       | null; false                    | 

### Association

- has_many :sales
- has_many :users, through: sales
- belongs_to :user
- belongs_to :adress

## sale テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| item   | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :item

## adresses テーブル

| Column           | Type    | Options     |
| ---------------- | ------- | ----------- |
| postal_code      | integer | null: false |
| prefectures      | text    | null: false |
| city             | text    | null: false |
| address          | text    | null: false |
| building_name    | text    | null: false |
| tel              | integer | null: false |

### Association

- belongs_to :user
- has_many :items