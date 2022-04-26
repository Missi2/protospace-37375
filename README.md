#　テーブル設計

## Users　テーブル
| Column             | Type   | Option                    |
| ------------------ | ------ | ------------------------- |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| name               | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

## prototypesテーブル
| Column     | Type       | Option                                             |
| ---------- | ---------- | -------------------------------------------------- |
| title      | string     | null: false                                        |
| catch_copy | text       | null: false                                        |
| concept    | text       | null: false                                        |
| user       | references | null: false, t.references :user, foreign_key: true |

## Commentsテーブル
| Column    | Type       | Option                                                   |
| --------- | ---------- | -------------------------------------------------------- |
| content   | text       | null: false                                              |
| prototype | references | null: false, t.references :prototypes, foreign_key: true |
| user      | references | null: false, t.references :user, foreign_key: true       |