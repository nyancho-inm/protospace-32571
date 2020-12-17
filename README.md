# テーブル設計

## users テーブル

| Colum      | Type   | Options     |
| ---------- | ------ | ----------- | 
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :rooms
- has_many :prototypes

## comments テーブル

| Colum     | Type       | Options     | 
| --------- | ---------- | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |

### Association

- belongs_to :user
- belongs_to :prototype

## prototypes テーブル

| Colum      | Type       | Options            | 
| ---------- | ---------- | ------------------ |
| title      | string     | null: false        |
| catch_copy | text       | null: false        |
| concept    | text       | null: false        |
| image      |            | ActiveStorageで実装 |
| user       | references |                    |

### Association

- belongs_to :user
- has_many :comments



