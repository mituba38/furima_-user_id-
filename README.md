# テーブル設計
## users テーブル

| Column           | Type    | Options     |
| ---------------- | ------- | ----------- |
| first_name       | string  | null: false |
| family_name      | string  | null: false |
| kanafirst_name   | string  | null: false |
| kanafirmily_name | string  | null: false |
| email            | string  | null: false |
| password         | string  | null: false |
| nickname         | string  | null: false |
| birth            | date    | null: false |

### Association

- has_many :sales
- has_many :items

## items テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| user        | references | null: false, foreign_key: true |
| explanation |
| name        | text       | null: false                    |  
| price       | integer    | null; false                    |   
| category    | integer    | null; false                    | 
| status      | integer    | null; false                    | 
| charge      | integer    | null; false                    | 
| area        | integer    | null; false                    | 
| date        | integer    | null; false                    | 

### Association

- has_many :sales
- belongs_to :user

## sale テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| item   | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :item
- has_one :adress

## adresses テーブル

| Column           | Type    | Options     |
| ---------------- | ------- | ----------- |
| postal_code      | string  | null: false |
| prefectures      | string  | null: false |
| city             | string  | null: false |
| address          | string  | null: false |
| building_name    | string  |             |
| tel              | string  | null: false |

### Association

- belongs_to :sale