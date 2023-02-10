# usersテーブル

| Column             | Type    | Options                   |
| ------------------ | ------- | ------------------------- |
| nickname           | string  | null: false               |
| email              | string  | null: false, unique: true |
| encrypted_password | string  | null: false               |

- has_many :pages


# pagesテーブル

| Column      | Type       | Options                         |
| ----------- | ---------- | ------------------------------- |
| title       | string     | null: false                     |
| url         | string     | null: false                     |
| user_id     | references | null: false,  foreign_key: true |
| category_id | references | null: false,  foreign_key: true |

- belongs_to :user
- belongs_to :category


# categoriesテーブル

| Column  | Type       |                                |
| ------- | ---------- | ------------------------------ |
| name    | string     | null: false                    |
| page_id | references | null: false, foreign_key: true |

- has_many :pages