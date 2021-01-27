# テーブル設計

## users テーブル

| Column    | Type   | Options     |
| --------- | ------ | ----------- |
| email     | string | not null    |
| password  | string | not null    |
| name      | string | not null    |
| profile   | text   | not null    |
| occupation| text   | not null    |
| position  | text   | not null    |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| title     | string     | not null    |
| catch_copy| string     | not null    |
| concept   | string     | not null    |
| image     |            |             |
| user      | references |             |

### Association

- belongs_to :users
- has_many :comments

## comments テーブル

| Column      | Type       | Options    |
| ----------- | ---------- | ---------- |
| text        | text       | not null   |
| user        | references | not null   |
| prototype   | references | not null   |

### Association

- belongs_to :prototypes
- belongs_to :user
