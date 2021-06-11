## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| email    | string | null: false |
| password | string | null: false |
| nickname | string | null: false |
| profile  | text   | null: false |

has_many   :tweets
has_many   :comments


## tweets テーブル

| Column   | Type       | Options                        |
| -------- | ---------- | ------------------------------ |
| text     | text       | null: false                    |
| user     | references | null: false, foreign_key: true |

  has_many   :comments
  belongs_to :user

## comments テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| tweet     | references | null: false, foreign_key: true |

  belongs_to :user
  belongs_to :tweet