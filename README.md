# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |

### Association

- has_many :protocols
- has_many :comment

## protocols テーブル

| Column       | Type   | Options     |
| ------       | ------ | ----------- |
| name         | string | null: false |
| catch_copy   | string | null: false |
| concept      | string | null: false |


### Association

- has_many :comment
- belongs_to :user

## comments テーブル

| Column  | Type       |Options                         |
| ------  | ---------- | ------------------------------ |
| user    | references | null: false, foreign_key: true |
| comment | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :protocol