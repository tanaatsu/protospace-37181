#　テーブル設計

## users　テーブル

|Column            |Type          |Option                |
|------------------|--------------|----------------------|
|email             |string        |NOT NULL,ユニーク制約   |
|encrypted_password|string        |NOT NULL              |
|name              |string        |NOT NULL              |
|profile           |text          |NOT NULL              |
|occupation        |text          |NOT NULL              |
|position          |text          |NOT NULL              |

## Association

- has_many :comments
- has_many :prototypes


## prototype　テーブル

|Column            |Type          |Option                 |
|------------------|--------------|-----------------------|
|title             |string        |NOT NULL               |
|catch_copy        |text          |NOT NULL               |
|concept           |text          |NOT NULL               |
|user              |references    |NOT NULL,外部キ-        |

## Association

- belongs_to :user
- has_many :comments


## comments　テーブル

|Column            |Type          |Option                 |
|------------------|--------------|-----------------------|
|content           |text          |NOT NULL               |
|prototype         |references    |NOT NULL,外部キ-        |
|user              |references    |NOT NULL,外部キ-        |


## Association

- belongs_to :user
- belongs_to :prototype

