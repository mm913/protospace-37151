# テーブル設計

## users テーブル

| Column             | Type   | Options             |
---------------------|--------|---------------------|
| email              | string | NOT NULL,ユニーク制約 |
| encrypted_password | string | NOT NULL            |
| name               | string | NOT NULL            |
| profile            | text   | NOT NULL            |
| occupation         | text   | NOT NULL            |
| position           | text   | NOT NULL            |

## Association
- has_many :prototypes
- has_many :comments


## prototypes テーブル

| Column      | Type       | Option          |
--------------|------------|-----------------|
| title       | string     | NOT NULL        |
| catch_copy  | text       | NOT NULL        |
| concept     | text       | NUT NULL        |
| user        | references | NOT NULL,外部キー |

## Association
- belongs_to :user
- has_many :comments


## comments テーブル

| Column      | Type       | Option           |
--------------|------------|------------------|
| content     | text       | NOT NULL         |
| prototype   | references | NOT NULL,外部キー |
| user        | references | NOT NULL,外部キー |

## Association
- belongs_to :user
- belongs_to :prototypes